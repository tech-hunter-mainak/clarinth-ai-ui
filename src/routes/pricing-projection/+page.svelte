<script lang="ts">
	import { onMount } from 'svelte';
	import * as XLSX from 'xlsx';

	/* ============================
     TYPES
  ============================ */

	interface TechnicalCosts {
		smtp: number;
		sms: number;
		third_party_api: number;
		payment_gateway: number;
		input_token: number;
		output_token: number;
		cloud_server: number;
	}

	interface Inputs {
		serviceModel: 'hybrid' | 'online' | 'offline';
		targetSegment: 'b2c' | 'b2b' | 'both';
		city: string;
        years: number;

		initialUsers: number;
		userGrowth: number;
		userLooseRate: number;
		modulesPerUser: number;
		targetProfitPerUser: number;

		techTeam: number;
		techSalary: number;
		opsTeam: number;
		opsSalary: number;
		rent: number;

		cac: number;
		marketingBudget: number;
		digitalMix: number;
		contentBudget: number;

		technical: TechnicalCosts;

		legalSetup: number;
		complianceCost: number;
		dataSecurity: number;
		insurance: number;

		initialCapital: number;
		seriesA: number;
		burnRate: number;
	}

	interface FinancialYear {
		year: number;
		totalRevenue: number;
		grossProfit: number;
		totalOpex: number;
		ebitda: number;
		ebitdaMargin: number;

		platformCostPerUser: number;
		modulePrice: number;

		cashInflow: number;
		cashOutflow: number;
		netCashFlow: number;
		cashBalance: number;

		avgUsers: number;
		cac: number;
		ltv: number;
		ltvCacRatio: number;
	}

	/* ============================
     STATE
  ============================ */

	let inputs: Inputs = {
		serviceModel: 'hybrid',
		targetSegment: 'b2c',
		city: 'bangalore',
        years: 5,

		initialUsers: 1000,
		userGrowth: 0.15,
		userLooseRate: 0.02,
		modulesPerUser: 3,
		targetProfitPerUser: 600,

		techTeam: 5,
		techSalary: 80000,
		opsTeam: 8,
		opsSalary: 40000,
		rent: 150000,

		cac: 1200,
		marketingBudget: 300000,
		digitalMix: 0.7,
		contentBudget: 80000,

		technical: {
			smtp: 200,
			sms: 500,
			third_party_api: 1000,
			payment_gateway: 0.02,
			input_token: 0.001,
			output_token: 0.001,
			cloud_server: 5000
		},

		legalSetup: 250000,
		complianceCost: 300000,
		dataSecurity: 400000,
		insurance: 200000,

		initialCapital: 10000000,
		seriesA: 50000000,
		burnRate: 18
	};

	let financialData: FinancialYear[] = [];
	let selectedYear: number = 1;

	/* ============================
     CORE MODEL
  ============================ */

	function calculateYearModel(inputs: Inputs): FinancialYear[] {
		const years = inputs.years;
		const data: FinancialYear[] = [];

		let cumulativeCash = inputs.initialCapital;
		let currentUsers = Math.max(1, inputs.initialUsers);

		for (let year = 1; year <= years; year++) {
			const annualGrowth = inputs.userGrowth * (1 - (year - 1) * 0.15);
			const churnMultiplier = 1 - inputs.userLooseRate;

			const avgUsers = currentUsers * Math.pow(1 + annualGrowth, 6) * churnMultiplier;

			currentUsers = currentUsers * Math.pow(1 + annualGrowth, 12) * churnMultiplier;

			/* ===== COST PER USER ===== */
            
            const techCosts = (inputs.technical.smtp +
					inputs.technical.sms +
					inputs.technical.third_party_api +
					inputs.technical.cloud_server) * 12;

			const fixedAnnualCosts =
				(inputs.rent +
					inputs.marketingBudget) *
				12 + techCosts + (inputs.technical.payment_gateway * techCosts);

			const infraCostPerUser = fixedAnnualCosts / Math.max(avgUsers, 1);

			const aiCostPerUserAnnual =
				(inputs.technical.input_token + inputs.technical.output_token) * inputs.modulesPerUser;

			const platformCostPerUser = infraCostPerUser + aiCostPerUserAnnual;

			const modulePrice = platformCostPerUser + inputs.targetProfitPerUser;

			/* ===== REVENUE ===== */

			const totalRevenue = avgUsers * inputs.modulesPerUser * modulePrice;

			/* ===== OPEX ===== */

			const techSalaries = inputs.techTeam * inputs.techSalary * 12 * (1 + (year - 1) * 0.08);

			const opsSalaries = inputs.opsTeam * inputs.opsSalary * 12 * (1 + (year - 1) * 0.08);

			const legalCost = year === 1 ? inputs.legalSetup : 0;

			const miscExpenses = totalRevenue * 0.05;

			const totalOpex =
				techSalaries +
				opsSalaries +
				fixedAnnualCosts +
				legalCost +
				inputs.complianceCost +
				inputs.dataSecurity +
				inputs.insurance +
				miscExpenses;

			const grossProfit = totalRevenue;
			const ebitda = grossProfit - totalOpex;

			const ebitdaMargin = totalRevenue > 0 ? (ebitda / totalRevenue) * 100 : 0;

			/* ===== CASHFLOW ===== */

			const cashInflow = totalRevenue + (year === 2 ? inputs.seriesA : 0);

			const cashOutflow = totalOpex;
			const netCashFlow = cashInflow - cashOutflow;

			cumulativeCash += netCashFlow;

			/* ===== METRICS ===== */

			const ltv = modulePrice * inputs.modulesPerUser * 1.5;

			const ltvCacRatio = inputs.cac > 0 ? ltv / inputs.cac : 0;

			data.push({
				year,
				totalRevenue,
				grossProfit,
				totalOpex,
				ebitda,
				ebitdaMargin,

				platformCostPerUser,
				modulePrice: modulePrice / inputs.modulesPerUser,

				cashInflow,
				cashOutflow,
				netCashFlow,
				cashBalance: cumulativeCash,

				avgUsers: Math.round(avgUsers),
				cac: inputs.cac,
				ltv,
				ltvCacRatio
			});
		}

		return data;
	}

	function runModel(): void {
		financialData = calculateYearModel(inputs);
		selectedYear = 1;
	}

	onMount(runModel);

	function formatINR(v: number): string {
		return '₹' + Math.round(v).toLocaleString('en-IN');
	}

	async function exportExcel(): Promise<void> {
		const rows = financialData.map((y) => ({
			Year: y.year,
			Revenue: y.totalRevenue,
			EBITDA: y.ebitda,
			Cash: y.cashBalance,
			Users: y.avgUsers,
			CAC: y.cac
		}));

		const wb = XLSX.utils.book_new();
		const ws = XLSX.utils.json_to_sheet(rows);
		XLSX.utils.book_append_sheet(wb, ws, 'Financial Model');
		XLSX.writeFile(wb, 'financial_model.xlsx');
	}
</script>

<main class="container">
	<div class="header">
		<h1>🧠 Mental Health Startup Financial Model</h1>
		<p class="subtitle">Comprehensive 5-Year Financial Projection for Indian Market</p>
	</div>

	<div class="section">
		<div class="section-title">Business Model</div>
		<div class="input-grid">
			<div class="input-group">
				<label>Service Model</label>
				<select bind:value={inputs.serviceModel}>
					<option value="hybrid">Hybrid</option>
					<option value="online">Online Only</option>
					<option value="offline">Offline Clinics</option>
				</select>
			</div>

			<div class="input-group">
				<label>Target Segment</label>
				<select bind:value={inputs.targetSegment}>
					<option value="b2c">B2C</option>
					<option value="b2b">B2B</option>
					<option value="both">B2C + B2B</option>
				</select>
			</div>

			<div class="input-group">
				<label>Starting City</label>
				<select bind:value={inputs.city}>
					<option value="bangalore">Bangalore</option>
					<option value="mumbai">Mumbai</option>
					<option value="delhi">Delhi NCR</option>
					<option value="hyderabad">Hyderabad</option>
					<option value="pune">Pune</option>
				</select>
			</div>
			<div class="input-group">
				<label>Projection Years</label>
				<input type="number" bind:value={inputs.years}>
			</div>
		</div>
	</div>

	<div class="section">
		<div class="section-title">Revenue Assumptions</div>
		<div class="input-grid">
			<div class="input-group">
				<label>Initial Monthly Users</label>
				<input type="number" bind:value={inputs.initialUsers} />
			</div>

			<div class="input-group">
				<label>Monthly User Growth %</label>
				<input type="number" step="0.01" bind:value={inputs.userGrowth} />
			</div>

			<div class="input-group">
				<label>Monthly User Churn %</label>
				<input type="number" step="0.01" bind:value={inputs.userLooseRate} />
			</div>

			<div class="input-group">
				<label>Modules / User / Month</label>
				<input type="number" bind:value={inputs.modulesPerUser} />
			</div>

			<div class="input-group">
				<label>Target Profit Per User (Annual)</label>
				<input type="number" bind:value={inputs.targetProfitPerUser} />
			</div>
		</div>
	</div>

	<div class="section">
		<div class="section-title">Operations & Fixed Costs</div>
		<div class="input-grid">
			<div class="input-group">
				<label>Tech Team Size</label>
				<input type="number" bind:value={inputs.techTeam} />
			</div>

			<div class="input-group">
				<label>Tech Salary / Month</label>
				<input type="number" bind:value={inputs.techSalary} />
			</div>

			<div class="input-group">
				<label>Ops Team Size</label>
				<input type="number" bind:value={inputs.opsTeam} />
			</div>

			<div class="input-group">
				<label>Ops Salary / Month</label>
				<input type="number" bind:value={inputs.opsSalary} />
			</div>

			<div class="input-group">
				<label>Office Rent / Month</label>
				<input type="number" bind:value={inputs.rent} />
			</div>
		</div>
	</div>

	<div class="section">
		<div class="section-title">Marketing & Customer Acquisition</div>
		<div class="input-grid">
			<div class="input-group">
				<label>Customer Acquisition Cost (CAC)</label>
				<input type="number" bind:value={inputs.cac} />
			</div>

			<div class="input-group">
				<label>Marketing Budget / Month</label>
				<input type="number" bind:value={inputs.marketingBudget} />
			</div>

			<div class="input-group">
				<label>Digital Marketing Mix %</label>
				<input type="number" step="0.01" bind:value={inputs.digitalMix} />
			</div>

			<div class="input-group">
				<label>Content Budget / Month</label>
				<input type="number" bind:value={inputs.contentBudget} />
			</div>
		</div>
	</div>

	<div class="section">
		<div class="section-title">Technical Infrastructure & AI Cost</div>
		<div class="input-grid">
			<div class="input-group">
				<label>SMTP / Month</label>
				<input type="number" bind:value={inputs.technical.smtp} />
			</div>

			<div class="input-group">
				<label>SMS / Month</label>
				<input type="number" bind:value={inputs.technical.sms} />
			</div>

			<div class="input-group">
				<label>Third Party API / Month</label>
				<input type="number" bind:value={inputs.technical.third_party_api} />
			</div>

			<div class="input-group">
				<label>Payment Gateway %</label>
				<input type="number" step="0.01" bind:value={inputs.technical.payment_gateway} />
			</div>

			<div class="input-group">
				<label>AI Input Token Cost / Module</label>
				<input type="number" step="0.0001" bind:value={inputs.technical.input_token} />
			</div>

			<div class="input-group">
				<label>AI Output Token Cost / Module</label>
				<input type="number" step="0.0001" bind:value={inputs.technical.output_token} />
			</div>

			<div class="input-group">
				<label>Cloud Cost / Month</label>
				<input type="number" bind:value={inputs.technical.cloud_server} />
			</div>
		</div>
	</div>

	<div class="section">
		<div class="section-title">Legal & Compliance</div>
		<div class="input-grid">
			<div class="input-group">
				<label>Company Setup Cost</label>
				<input type="number" bind:value={inputs.legalSetup} />
			</div>

			<div class="input-group">
				<label>Annual Compliance</label>
				<input type="number" bind:value={inputs.complianceCost} />
			</div>

			<div class="input-group">
				<label>Data Security</label>
				<input type="number" bind:value={inputs.dataSecurity} />
			</div>

			<div class="input-group">
				<label>Insurance</label>
				<input type="number" bind:value={inputs.insurance} />
			</div>
		</div>
	</div>

	<div class="section">
		<div class="section-title">Funding & Capital Structure</div>
		<div class="input-grid">
			<div class="input-group">
				<label>Initial Capital</label>
				<input type="number" bind:value={inputs.initialCapital} />
			</div>

			<div class="input-group">
				<label>Series A Funding (Year 2)</label>
				<input type="number" bind:value={inputs.seriesA} />
			</div>

			<div class="input-group">
				<label>Burn Rate (Months Runway Target)</label>
				<input type="number" bind:value={inputs.burnRate} />
			</div>
		</div>
	</div>

	<div style="text-align:center;">
		<button class="btn" on:click={runModel}> Generate Financial Projection </button>
	</div>

	{#if financialData.length}
		<div class="year-tabs" style="padding:20px;">
			{#each financialData as d}
				<button class:selected={selectedYear === d.year} on:click={() => (selectedYear = d.year)}
					>Year {d.year}</button
				>
			{/each}
		</div>

		{@const d = financialData[selectedYear - 1]}

		<div class="results-grid" style="padding:20px;">
			<div class="result-card revenue">
				<h3>Revenue</h3>
				<div class="big-number">{formatINR(d.totalRevenue)}</div>
			</div>
			<div class="result-card profit">
				<h3>EBITDA</h3>
				<div class="big-number">{formatINR(d.ebitda)}</div>
			</div>
			<div class="result-card users">
				<h3>Users</h3>
				<div class="big-number">{d.avgUsers.toLocaleString()}</div>
			</div>
			<div class="result-card cash">
				<h3>Cash Balance</h3>
				<div class="big-number">{formatINR(d.cashBalance)}</div>
			</div>
			<div class="result-card">
				<h3>Module Price</h3>
				<div class="big-number">{formatINR(d.modulePrice)}</div>
			</div>
		</div>

		<table class="projection-table" style="margin:20px;">
			<thead>
				<tr><th>Metric</th><th>Value</th></tr>
			</thead>
			<tbody>
				<tr><td>Total Revenue</td><td>{formatINR(d.totalRevenue)}</td></tr>
				<tr><td>Platform Cost / User</td><td>{formatINR(d.platformCostPerUser)}</td></tr>
				<tr><td>Gross Profit</td><td>{formatINR(d.grossProfit)}</td></tr>
				<tr
					><td>EBITDA</td><td class={d.ebitda >= 0 ? 'positive' : 'negative'}
						>{formatINR(d.ebitda)}</td
					></tr
				>
				<tr><td>Total Opex</td><td>{formatINR(d.totalOpex)}</td></tr>
				<tr><td>Cash Inflow</td><td>{formatINR(d.cashInflow)}</td></tr>
				<tr><td>Cash Outflow</td><td>{formatINR(d.cashOutflow)}</td></tr>
				<tr><td>Net Cashflow</td><td>{formatINR(d.netCashFlow)}</td></tr>
				<tr><td>Cash Balance</td><td>{formatINR(d.cashBalance)}</td></tr>
				<tr><td>Users</td><td>{d.avgUsers}</td></tr>
				<tr><td>CAC</td><td>{formatINR(d.cac)}</td></tr>
				<tr><td>LTV</td><td>{formatINR(d.ltv)}</td></tr>
				<tr><td>LTV CAC Ratio</td><td>{formatINR(d.ltvCacRatio)}</td></tr>
			</tbody>
		</table>

		<div style="text-align:center;margin:20px;">
			<button class="download-btn btn" on:click={exportExcel}> Download Excel Report </button>
		</div>
	{/if}
</main>

<style>
	/* Keep your existing styles (trimmed here for brevity if desired) */
	body {
		font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		min-height: 100vh;
		padding: 20px;
	}
	.container {
		max-width: 1400px;
		margin: 0 auto;
		background: white;
		border-radius: 16px;
		box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
		overflow: hidden;
	}
	.header {
		background: linear-gradient(135deg, #2d3748 0%, #1a202c 100%);
		color: white;
		padding: 30px;
		text-align: center;
	}
	h1 {
		font-size: 28px;
		margin-bottom: 10px;
	}
	.subtitle {
		opacity: 0.9;
		font-size: 14px;
	}
	.section {
		margin-bottom: 30px;
		background: #f7fafc;
		padding: 20px;
		border-radius: 8px;
		border-left: 4px solid #667eea;
	}
	.section-title {
		font-size: 20px;
		color: #2d3748;
		margin-bottom: 15px;
		font-weight: 600;
	}
	.input-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 15px;
		margin-top: 15px;
	}
	.input-group {
		display: flex;
		flex-direction: column;
	}
	label {
		font-size: 13px;
		color: #4a5568;
		margin-bottom: 5px;
		font-weight: 500;
	}
	input,
	select {
		padding: 10px;
		border: 2px solid #e2e8f0;
		border-radius: 6px;
		font-size: 14px;
		transition: all 0.3s;
	}
	input:focus,
	select:focus {
		outline: none;
		border-color: #667eea;
		box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
	}
	.btn {
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		color: white;
		padding: 15px 40px;
		border: none;
		border-radius: 8px;
		font-size: 16px;
		font-weight: 600;
		cursor: pointer;
		transition:
			transform 0.2s,
			box-shadow 0.2s;
		margin: 20px auto;
		display: block;
	}
	.btn:hover {
		transform: translateY(-2px);
		box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
	}
	.result-card {
		display: inline-block;
		width: 18%;
		margin-right: 1%;
		background: white;
		padding: 15px;
		border-radius: 8px;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.06);
		text-align: center;
	}
	.big-number {
		font-size: 20px;
		font-weight: 700;
		color: #2d3748;
	}
	.projection-table {
		width: 100%;
		border-collapse: collapse;
		margin-top: 15px;
		background: white;
		border-radius: 8px;
		overflow: hidden;
	}
	th,
	td {
		padding: 12px;
		text-align: right;
		border-bottom: 1px solid #e2e8f0;
	}
	th {
		background: #2d3748;
		color: white;
		font-weight: 600;
		text-align: left;
	}
	td:first-child,
	th:first-child {
		text-align: left;
	}
	.positive {
		color: #38a169;
	}
	.negative {
		color: #e53e3e;
	}
</style>
