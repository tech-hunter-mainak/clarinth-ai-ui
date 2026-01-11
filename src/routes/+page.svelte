<script lang="ts">
	const performance = [
		{ label: 'New Leads', value: 75.2 },
		{ label: 'Qualified', value: 56.7 },
		{ label: 'Proposal', value: 48.6 },
		{ label: 'Closed', value: 39.7 }
	];

	const features = [
		'Personalized Engagement',
		'Smart Data Analytics',
		'Seamless Integration',
		'24/7 Customer Support'
	];

	const stats = [
		{ value: '200+', label: 'Business Partners' },
		{ value: '30K+', label: 'Satisfied Customers' },
		{ value: '10+', label: 'Years of Excellence' }
	];
</script>

<div class="flex min-h-screen w-full flex-col justify-center bg-[#f3f7f5]">
	<div
		class="relative z-10 flex w-full flex-col items-center overflow-hidden rounded-2xl bg-white shadow-xl"
	>
		<!-- Hero Section -->
		<section class="relative flex min-w-screen! flex-col items-center bg-white">
			<!-- HERO IMAGE -->
			<div class="relative h-90 overflow-hidden rounded-[50px] md:w-[calc(100%-60px)]">
				<img
					src="/hero-image.jpg"
					alt="Woman waiting at airport"
					class="h-full w-full object-cover"
				/>

				<!-- DARK OVERLAY -->
				<div class="absolute inset-0 flex items-center bg-black/40 px-10">
					<div class="max-w-md">
						<h1 class="mb-3 text-3xl font-semibold text-white">Private Covid Travel Tests</h1>
						<p class="mb-6 text-gray-200">
							We’re an award winning provider of COVID-19 tests, with a 24/7 customer service team.
						</p>

						<div class="flex space-x-4">
							<button class="rounded-lg bg-white px-6 py-3 font-medium text-black shadow-md">
								Day 2 Test
							</button>

							<button class="rounded-lg bg-[#6F6CFF] px-6 py-3 font-medium text-white shadow-md">
								Antigen Fit to Fly Test
							</button>
						</div>
					</div>
				</div>
			</div>

			<!-- THREE INFORMATION BOXES UNDER HERO -->
			<div class="relative z-20 -mt-12 grid grid-cols-1 gap-6 px-8 md:grid-cols-3 lg:px-20">
				<div class="rounded-lg border bg-white p-6 text-center shadow-md">
					<h3 class="text-lg font-semibold">24/7 Customer Service</h3>
				</div>

				<div class="rounded-lg border bg-white p-6 text-center shadow-md">
					<h3 class="text-lg font-semibold">6,000+ 5 star Reviews</h3>
				</div>

				<div class="rounded-lg border bg-white p-6 text-center shadow-md">
					<h3 class="text-lg font-semibold">Government Registered</h3>
				</div>
			</div>
		</section>

		<div class="w-full bg-white px-6 py-14 md:px-12 lg:px-20">
			<div class="mx-auto grid max-w-7xl grid-cols-1 items-center gap-12 md:grid-cols-2 md:gap-20">
				<!-- LEFT side -->
				<div class="relative flex w-full justify-center">
					<!-- Laptop Image -->
					<div class="w-full max-w-lg overflow-hidden rounded-xl shadow-md">
						<img src="/your-image.jpg" alt="Laptop user" class="h-full w-full object-cover" />
					</div>

					<!-- Floating Card -->
					<div
						class="absolute -top-6 left-6 w-64 rounded-lg border border-gray-100 bg-white px-5 py-4 shadow-xl"
					>
						<h3 class="mb-4 text-sm font-semibold">Sales Performance Overview</h3>
						<div class="space-y-4">
							{#each performance as item}
								<div>
									<div class="mb-1 flex justify-between text-xs font-medium text-gray-700">
										<span>{item.label}</span>
										<span>{item.value}%</span>
									</div>
									<div class="h-[6px] w-full rounded-full bg-gray-200">
										<div
											class="h-[6px] rounded-full bg-green-600 transition-all"
											style="width: {item.value}%;"
										></div>
									</div>
								</div>
							{/each}
						</div>
					</div>
				</div>

				<!-- RIGHT side -->
				<div class="w-full space-y-6">
					<h2 class="text-3xl leading-snug font-bold lg:text-4xl">
						Customer-Driven Solutions<br />
						with Xentrix
					</h2>

					<p class="max-w-md text-[15px] leading-relaxed text-gray-600">
						At Xentrix, we focus on delivering tailored solutions that meet your customers' needs.
						With advanced technology and AI-powered CRM systems, we help businesses build stronger
						customer relationships.
					</p>

					<!-- Feature grid (2 columns) -->
					<div class="grid grid-cols-1 gap-x-10 gap-y-4 sm:grid-cols-2">
						{#each features as f}
							<div class="flex items-center space-x-2">
								<div class="h-4 w-4 rounded-full bg-green-600"></div>
								<span class="text-[15px] text-gray-800">{f}</span>
							</div>
						{/each}
					</div>

					<!-- Stats -->
					<div class="flex flex-wrap gap-10 pt-4">
						{#each stats as s}
							<div class="min-w-[100px]">
								<p class="text-3xl font-bold">{s.value}</p>
								<p class="text-sm text-gray-600">{s.label}</p>
							</div>
						{/each}
					</div>
				</div>
			</div>
		</div>

		<section class="w-full bg-white py-20">
			<div class="mx-auto max-w-6xl px-6 text-center">
				<h1 class="text-4xl font-semibold tracking-tight text-gray-900 md:text-5xl">
					Smart Automation,<br class="hidden md:block" />
					Limitless Possibilities
				</h1>

				<p class="mx-auto mt-4 max-w-2xl text-base leading-relaxed text-gray-600 md:text-lg">
					With Xentrix, you get a powerful automation platform designed to optimize your workflow
					and scale your business effortlessly.
				</p>

				<div class="mt-14 grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-4">
					<!-- Card 1 -->
					<div class="rounded-xl bg-gray-100 px-6 py-10 text-left">
						<div
							class="flex h-10 w-10 items-center justify-center rounded-md bg-green-700 text-white"
						>
							<!-- icon placeholder -->
							<span class="block h-5 w-5 rounded-sm bg-white opacity-90"></span>
						</div>

						<h3 class="mt-6 text-lg font-semibold text-gray-900">AI-Powered Insights</h3>
						<p class="mt-2 text-sm leading-relaxed text-gray-600">
							Make data-driven decisions with real-time analytics.
						</p>
					</div>

					<!-- Card 2 -->
					<div class="rounded-xl bg-gray-100 px-6 py-10 text-left">
						<div
							class="flex h-10 w-10 items-center justify-center rounded-md bg-green-700 text-white"
						>
							<!-- icon placeholder -->
							<span class="block h-5 w-5 rounded-full bg-white opacity-90"></span>
						</div>

						<h3 class="mt-6 text-lg font-semibold text-gray-900">Workflow Automation</h3>
						<p class="mt-2 text-sm leading-relaxed text-gray-600">
							Streamline repetitive tasks and boost efficiency.
						</p>
					</div>

					<!-- Card 3 -->
					<div class="rounded-xl bg-gray-100 px-6 py-10 text-left">
						<div
							class="flex h-10 w-10 items-center justify-center rounded-md bg-green-700 text-white"
						>
							<!-- icon placeholder -->
							<span class="block h-5 w-4 bg-white opacity-90"></span>
						</div>

						<h3 class="mt-6 text-lg font-semibold text-gray-900">Omni-Channel Marketing</h3>
						<p class="mt-2 text-sm leading-relaxed text-gray-600">
							Engage your audience across multiple platforms seamlessly.
						</p>
					</div>

					<!-- Card 4 -->
					<div class="rounded-xl bg-gray-100 px-6 py-10 text-left">
						<div
							class="flex h-10 w-10 items-center justify-center rounded-md bg-green-700 text-white"
						>
							<!-- icon placeholder -->
							<span class="block h-5 w-4 rounded-sm bg-white opacity-90"></span>
						</div>

						<h3 class="mt-6 text-lg font-semibold text-gray-900">Secure Cloud Integration</h3>
						<p class="mt-2 text-sm leading-relaxed text-gray-600">
							Sync and access your data anytime, anywhere.
						</p>
					</div>
				</div>
			</div>
		</section>

		<section
			class="relative flex w-[calc(100%-40px)] flex-col items-start justify-between overflow-hidden rounded-xl bg-[#F4F7FB] px-8 py-16 md:flex-row md:items-center md:px-20"
		>
			<!-- Background subtle abstract contour lines -->
			<div class="pointer-events-none absolute inset-0 opacity-20">
				<svg
					viewBox="0 0 600 400"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
					class="h-full w-full"
				>
					<path
						d="M100 200c80-80 200-80 280 0s200 80 280 0"
						stroke="#dbe1ea"
						stroke-width="2"
						fill="none"
					/>
					<path
						d="M50 250c100-100 300-100 400 0s300 100 400 0"
						stroke="#e3e8ef"
						stroke-width="2"
						fill="none"
					/>
				</svg>
			</div>

			<!-- Text Block -->
			<div class="relative z-10 max-w-xl">
				<p class="mb-3 text-xs tracking-widest text-[#4A5A78]">CHANGE YOUR LIFE</p>

				<h1 class="text-4xl leading-tight font-semibold text-[#0B163F] md:text-5xl">
					<span class="font-bold">It’s Time</span> To Change Your Life Today
				</h1>
			</div>

			<!-- Button -->
			<div class="relative z-10 mt-8 md:mt-0">
				<button
					class="flex items-center gap-2 rounded-full bg-[#0A66FF] px-8 py-3 text-sm font-medium text-white shadow-sm transition hover:bg-blue-700"
				>
					Contact Your Doctor
					<svg
						width="16"
						height="16"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
						class="inline-block"
					>
						<path
							d="M4 8h8M10 4l4 4-4 4"
							stroke="white"
							stroke-width="2"
							stroke-linecap="round"
							stroke-linejoin="round"
						/>
					</svg>
				</button>
			</div>
		</section>

		<!-- Footer Section -->
		<footer class="border-t bg-white py-14">
			<div class="mb-6 text-center text-lg font-semibold">Approved and Trusted Provider</div>

			<div class="flex justify-center space-x-20">
				<img src="/dept-health.svg" class="h-12" alt="Department of Health & Social Care" />
				<img src="/govuk.svg" class="h-12" alt="GOV.UK Logo" />
			</div>
		</footer>
	</div>
</div>
