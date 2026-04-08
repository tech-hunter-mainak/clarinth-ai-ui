<svelte:head>
	<title>Saathi Privacy Policy</title>
</svelte:head>

<div class="page">
	<aside class="toc">
		<h3>Privacy Policy</h3>
		<a href="#promise">Saathi's Promise</a>
		<a href="#scope">1. Scope of This Policy</a>
		<a href="#data-we-collect">2. Data We Collect</a>
		<a href="#how-we-use">3. How We Use Your Data</a>
		<a href="#sensitive-data">4. Sensitive Mental Health Data</a>
		<a href="#sharing">5. Data Sharing</a>
		<a href="#retention">6. Data Retention</a>
		<a href="#security">7. Security</a>
		<a href="#rights">8. Your Rights and Choices</a>
		<a href="#minors">9. Minors</a>
		<a href="#transfers">10. International Data Transfers</a>
		<a href="#changes">11. Changes to This Policy</a>
		<a href="#contact">12. Contact Us</a>
	</aside>

	<main class="content">
		<span class="effective-date">Effective: 1 April 2025</span>
		<h1>Privacy Policy</h1>
		<p class="subtitle">
			This policy describes what data Saathi ("we", "us", "our") collects from you, why we collect it, how it is
			protected, and what rights you have over it. Saathi is a product of [Company Legal Name], registered in India.
		</p>

		<div class="promise-box" id="promise">
			<h2>Saathi's Promise</h2>
			<p>
				Mental health is deeply personal. We built Saathi on the conviction that a safe space to reflect and heal
				must be a genuinely private one. Everything you share with Saathi — your mood, your thoughts, your
				responses to exercises — is yours.
			</p>
			<p>
				We will never sell, rent, or trade your personal or mental health data. We will not use your therapy
				content to train AI models without your explicit, opt-in consent. We will only share your information with
				third parties when strictly necessary to deliver the service, and only under binding privacy obligations.
			</p>
			<p>
				We commit to transparency, security, and putting your wellbeing above commercial interests.
			</p>
		</div>

		<section id="scope">
			<h2>1. Scope of This Policy</h2>
			<p>
				This policy applies to all users of the Saathi platform, including the web application at
				<a href="https://saathi.app">saathi.app</a> and any associated mobile clients. It covers data collected
				during onboarding, clinical assessments, CBT/DBT guided journeys, chat sessions, and account management.
			</p>
			<p>
				Saathi is intended for adults aged 18 and over. We do not knowingly collect data from anyone under 18.
				See <a href="#minors">Section 9</a> for more.
			</p>
			<p>
				This policy does not cover external websites or services that may be linked from within Saathi. If you
				follow a link to an external resource, that resource's own privacy policy applies.
			</p>
		</section>

		<section id="data-we-collect">
			<h2>2. Data We Collect</h2>

			<h3>Account and Identity</h3>
			<p>
				When you sign up, we collect your email address and verify it via a one-time password (OTP). We do not
				collect your full name, phone number, or government ID unless you voluntarily provide them. Your account
				is identified internally by an anonymous user ID.
			</p>

			<h3>Clinical Assessment Data</h3>
			<p>
				To recommend an appropriate care journey, Saathi asks you to complete validated clinical screening tools
				including the PHQ-9 (depression) and GAD-7 (anxiety). Your responses and computed scores are stored
				securely and used solely to personalise your journey. They are never shared externally.
			</p>

			<div class="sensitive-note">
				⚠️ PHQ-9 and GAD-7 scores constitute sensitive health information. They are treated with the highest
				level of data protection we apply and are never used for advertising or marketing purposes.
			</div>

			<h3>Journey and Module Progress</h3>
			<p>
				As you progress through CBT and DBT modules, we store your completion status, exercise responses,
				reflections, and any self-reported mood or symptom check-ins. This data drives personalised
				recommendations and allows you to resume your journey across sessions.
			</p>

			<h3>Conversation Data</h3>
			<p>
				Messages you exchange with Saathi's AI companion are processed in real time to generate responses.
				Conversations are stored to maintain session continuity and to allow your care path to adapt over time.
				We do not use conversation content to train AI models without your explicit, separate consent.
			</p>

			<h3>Usage and Technical Data</h3>
			<p>
				We collect standard technical data such as your IP address, browser type, operating system, session
				timestamps, and feature interactions. This helps us diagnose issues, monitor service reliability, and
				improve the platform. This data is not linked to your clinical or conversation records.
			</p>

			<h3>Payment Data</h3>
			<p>
				Subscription payments are processed by Stripe. We do not store your full card number or CVV on our
				servers. We receive and retain only a payment token, your subscription tier, and billing history, which
				are required to manage your account. Stripe's own privacy policy governs Stripe's handling of your
				payment details.
			</p>
		</section>

		<section id="how-we-use">
			<h2>3. How We Use Your Data</h2>
			<p>We use your data only for purposes that are directly connected to delivering and improving Saathi:</p>
			<ul>
				<li>To create and manage your account and authenticate your identity</li>
				<li>To assess your clinical needs and recommend an appropriate guided journey</li>
				<li>To personalise CBT/DBT module recommendations using your assessment scores and progress</li>
				<li>To power the AI companion conversation with contextual memory of your journey</li>
				<li>To send you transactional emails such as session reminders, OTP codes, and account notifications</li>
				<li>To process subscription payments and manage billing</li>
				<li>To detect, investigate, and prevent fraud, abuse, or safety-critical events</li>
				<li>To maintain, debug, and improve the reliability and safety of the platform</li>
			</ul>
			<p>
				We do <strong>not</strong> use your data to serve targeted advertising, build advertising profiles,
				or share data with marketing partners.
			</p>
		</section>

		<section id="sensitive-data">
			<h2>4. Sensitive Mental Health Data</h2>
			<p>
				Mental health data — including your assessment responses, symptom self-reports, mood logs, therapy
				exercise responses, and conversation content — is classified as sensitive personal data. We apply the
				following protections to this category of data specifically:
			</p>
			<ul>
				<li>Stored encrypted at rest using AES-256</li>
				<li>Transmitted exclusively over TLS 1.3</li>
				<li>Accessible only to systems with a direct clinical function (journey recommendation, module
						progression, session continuity)</li>
				<li>Not accessible to sales, marketing, or customer support staff without your explicit consent</li>
				<li>Not used as training data for AI models without a separate, explicit, opt-in consent action</li>
				<li>Not shared with third parties except as described in Section 5 below</li>
			</ul>
			<p>
				If you are ever at imminent risk of harm to yourself or others, Saathi's safety protocols may route
				you to emergency resources. In a genuine crisis, we may be legally obligated to act to protect your
				safety or the safety of others, even if that requires disclosure. We will always try to inform you
				before doing so, unless doing so would itself put someone at risk.
			</p>
		</section>

		<section id="sharing">
			<h2>5. Data Sharing</h2>
			<p>
				We do not sell or rent your data. We share your information only in the following limited circumstances:
			</p>

			<h3>Service Providers</h3>
			<p>
				We work with a small number of third-party vendors who help us operate Saathi. These providers process
				data strictly under our instructions and are bound by data processing agreements. They may not use your
				data for any purpose beyond the service they provide to us:
			</p>
			<ul>
				<li><strong>OpenAI</strong> — powers the AI companion. Conversation messages are transmitted to OpenAI's
					API for response generation. OpenAI's data usage policies apply; we have enabled Zero Data Retention
					where available.</li>
				<li><strong>Stripe</strong> — processes subscription payments.</li>
				<li><strong>Google Cloud / Cloud Run</strong> — hosts Saathi's backend API.</li>
				<li><strong>Vercel</strong> — hosts the web frontend.</li>
				<li><strong>Neo4j Aura</strong> — stores your journey graph, module progress, and recommendation data.</li>
				<li><strong>Upstash Redis</strong> — manages session state and short-term conversation context.</li>
			</ul>

			<h3>Legal Requirements</h3>
			<p>
				We may disclose your data if required to do so by law, court order, or government authority, or where we
				have a good-faith belief that disclosure is necessary to prevent harm, fraud, or illegal activity. We
				will challenge requests that we believe are overbroad or incompatible with your rights under applicable law.
			</p>

			<h3>Business Transfers</h3>
			<p>
				If Saathi is acquired, merged, or its assets are transferred, your data may be part of that transaction.
				We will notify you before your data becomes subject to a materially different privacy policy, and you
				will have the option to delete your account at that time.
			</p>

			<h3>With Your Consent</h3>
			<p>
				In any situation not described above, we will ask for your explicit consent before sharing your data.
			</p>
		</section>

		<section id="retention">
			<h2>6. Data Retention</h2>
			<p>
				We retain your account and journey data for as long as your account is active. If you delete your
				account, we will delete or irreversibly anonymise your personal and clinical data within 30 days,
				except where a longer retention period is required by law (for example, financial records relating to
				your subscription).
			</p>
			<p>
				Session context stored in Redis (used for real-time conversation memory) is ephemeral and expires
				automatically after a configurable inactivity period. It is not retained as a long-term record.
			</p>
			<p>
				Anonymised and aggregated data (for example, aggregate module completion rates across all users) may
				be retained indefinitely for platform improvement purposes. This data cannot identify you.
			</p>
		</section>

		<section id="security">
			<h2>7. Security</h2>
			<p>
				We implement security measures appropriate to the sensitivity of the data we hold:
			</p>
			<ul>
				<li>All data in transit is encrypted using TLS 1.3</li>
				<li>All data at rest is encrypted using AES-256</li>
				<li>Access to production systems is restricted by role and requires multi-factor authentication</li>
				<li>Backend APIs are authenticated; Saathi's frontend is the only authorised client</li>
				<li>Security patches and dependency updates are applied on a regular schedule</li>
			</ul>
			<p>
				No system is entirely without risk. If you become aware of a security vulnerability in Saathi, please
				report it responsibly to <a href="mailto:security@saathi.app">security@saathi.app</a>. We will
				acknowledge your report within 72 hours.
			</p>
		</section>

		<section id="rights">
			<h2>8. Your Rights and Choices</h2>
			<p>You have the following rights over your data at any time:</p>
			<ul>
				<li><strong>Access</strong> — you may request a copy of the personal data we hold about you</li>
				<li><strong>Correction</strong> — you may ask us to correct inaccurate data</li>
				<li><strong>Deletion</strong> — you may request deletion of your account and associated personal data</li>
				<li><strong>Portability</strong> — you may request your data in a structured, machine-readable format</li>
				<li><strong>Objection</strong> — you may object to specific types of processing (for example, receiving
					non-transactional communications)</li>
				<li><strong>Withdrawal of consent</strong> — where processing is based on your consent, you may
					withdraw it at any time without affecting the lawfulness of prior processing</li>
			</ul>
			<p>
				To exercise any of these rights, contact us at <a href="mailto:privacy@saathi.app">privacy@saathi.app</a>.
				We will respond within 30 days. We do not charge a fee for reasonable requests.
			</p>
			<p>
				If you are based in India, your rights are governed by the Digital Personal Data Protection Act, 2023
				(DPDP Act). If you are based in the EU or UK, the GDPR applies. We honour these rights for all users
				regardless of jurisdiction.
			</p>
		</section>

		<section id="minors">
			<h2>9. Minors</h2>
			<p>
				Saathi is not designed for, nor intended to be used by, anyone under the age of 18. We do not knowingly
				collect personal or clinical data from minors. If we become aware that a user is under 18, we will
				delete their account and associated data promptly.
			</p>
			<p>
				If you believe a minor has created a Saathi account, please contact us at
				<a href="mailto:privacy@saathi.app">privacy@saathi.app</a>.
			</p>
		</section>

		<section id="transfers">
			<h2>10. International Data Transfers</h2>
			<p>
				Saathi's infrastructure is primarily hosted in the United States (Google Cloud Run, Vercel) and in
				regions selected for latency and compliance (Neo4j Aura, Upstash Redis). If you are based in India,
				the EU, or the UK, your data may be transferred to and processed in the United States.
			</p>
			<p>
				Where such transfers occur, we rely on appropriate safeguards including standard contractual clauses
				(SCCs) and data processing agreements with our service providers. If you have questions about the
				specific safeguards applicable to your data, please contact us.
			</p>
		</section>

		<section id="changes">
			<h2>11. Changes to This Policy</h2>
			<p>
				We may update this policy as Saathi evolves. When we make material changes, we will notify you by
				email (to the address on your account) and display a notice within the app at least 14 days before
				the changes take effect.
			</p>
			<p>
				If you do not agree with the revised policy, you may delete your account before the effective date.
				Continued use of Saathi after the effective date constitutes acceptance of the updated policy.
			</p>
			<p>
				The effective date at the top of this page indicates when the current version came into force.
			</p>
		</section>

		<section id="contact">
			<h2>12. Contact Us</h2>
			<p>
				If you have questions about this policy, how your data is handled, or how to exercise your rights,
				please reach out:
			</p>
			<div class="contact-card">
				<p><strong>Email:</strong> <a href="mailto:privacy@saathi.app">privacy@saathi.app</a></p>
				<p><strong>Security disclosures:</strong> <a href="mailto:security@saathi.app">security@saathi.app</a></p>
				<p><strong>Company:</strong> [Company Legal Name]</p>
				<p><strong>Address:</strong> [Registered Address, India]</p>
				<p><strong>Data Protection contact:</strong> [Name / Role, if applicable]</p>
			</div>
		</section>
	</main>
</div>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}

	:global(body) {
		margin: 0;
		font-family:
			Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
			'Helvetica Neue', Arial, 'Noto Sans', sans-serif;
		background: #f7f6f2;
		color: #18212b;
	}

	:global(*) {
		box-sizing: border-box;
	}

	.page {
		min-height: 100vh;
		background:
			radial-gradient(circle at top left, rgba(220, 236, 231, 0.75), transparent 28%),
			radial-gradient(circle at top right, rgba(230, 221, 208, 0.65), transparent 26%),
			radial-gradient(circle at bottom center, rgba(215, 226, 236, 0.55), transparent 22%),
			#f7f6f2;
		display: flex;
		gap: 1.5rem;
		padding: 1.5rem;
	}

	.toc {
		width: 18rem;
		flex-shrink: 0;
		position: sticky;
		top: 1.5rem;
		align-self: flex-start;
		max-height: calc(100vh - 3rem);
		overflow-y: auto;
		border-radius: 1.75rem;
		background: rgba(255, 255, 255, 0.86);
		backdrop-filter: blur(10px);
		padding: 1.5rem;
		box-shadow: 0 10px 30px rgba(16, 50, 74, 0.08);
		border: 1px solid rgba(0, 0, 0, 0.05);
	}

	.toc h3 {
		margin: 0 0 1rem;
		font-size: 0.75rem;
		letter-spacing: 0.22em;
		text-transform: uppercase;
		font-weight: 700;
		color: #10324a;
	}

	.toc a {
		display: block;
		padding: 0.6rem 0.8rem;
		margin-bottom: 0.15rem;
		border-radius: 0.85rem;
		text-decoration: none;
		color: #5f6b78;
		font-size: 0.92rem;
		line-height: 1.35;
		transition:
			background 0.2s ease,
			color 0.2s ease,
			transform 0.2s ease;
	}

	.toc a:hover {
		background: #eef4f1;
		color: #10324a;
		transform: translateX(2px);
	}

	.content {
		flex: 1;
		max-width: 56rem;
		padding: 0.25rem 0 2rem;
	}

	.effective-date {
		display: inline-flex;
		align-items: center;
		border-radius: 999px;
		background: #ffffff !important;
		color: #10324a;
		padding: 0.45rem 0.9rem;
		font-size: 0.8rem;
		font-weight: 700;
		letter-spacing: 0.02em;
		box-shadow: 0 1px 2px rgba(16, 50, 74, 0.08);
	}

	h1 {
		margin: 1rem 0 0.75rem;
		font-size: clamp(2rem, 4vw, 3.75rem);
		line-height: 1.05;
		letter-spacing: -0.04em;
		font-weight: 700;
		color: #12222f;
	}

	.subtitle {
		margin: 0 0 1.75rem;
		padding-bottom: 1.5rem;
		border-bottom: 1px solid rgba(0, 0, 0, 0.08);
		font-size: 1rem;
		line-height: 1.8;
		color: #5f6b78;
	}

	.promise-box {
		background: white;
		border: 1px solid rgba(16, 50, 74, 0.08);
		/* border-radius: 2rem; */
		padding: 1.5rem 1.5rem 1.35rem;
		margin-bottom: 1.5rem;
		box-shadow: 0 20px 60px rgba(16, 50, 74, 0.1);
	}

	.promise-box h2 {
		margin: 0 0 0.8rem;
		font-size: 0.78rem;
		letter-spacing: 0.22em;
		text-transform: uppercase;
		font-weight: 700;
		color: #10324a;
	}

	.promise-box p {
		margin: 0 0 0.8rem;
		color: #1f2a35;
		font-size: 0.98rem;
		line-height: 1.8;
	}

	section {
		margin-top: 1.25rem;
	}

	section > h2 {
		margin: 0 0 1rem;
		padding: 0.8rem;
		border-left: 10px solid #686e6d !important;
		font-size: 1.4rem;
		line-height: 1.2;
        font-family: Georgia, 'Times New Roman', Times, serif;
		letter-spacing: -0.02em;
		font-weight: 700;
        color: #ffffff;
		background-color: #12222f !important;
	}

	section h3 {
		margin: 1.25rem 0 0.45rem;
		font-size: 0.98rem;
		font-weight: 700;
		color: #10324a;
	}

	p {
		margin: 0 0 0.85rem;
		font-size: 0.98rem;
		line-height: 1.8;
		color: #334155;
	}

	ul,
	ol {
		padding-left: 1.35rem;
		margin: 0 0 0.85rem;
	}

	li {
		margin-bottom: 0.45rem;
		font-size: 0.98rem;
		line-height: 1.75;
		color: #334155;
	}

	a {
		color: #10324a;
		text-decoration-thickness: 1px;
		text-underline-offset: 2px;
	}

	strong {
		font-weight: 700;
		color: #18212b;
	}

	.sensitive-note {
		margin: 1rem 0;
		padding: 1rem 1.1rem;
		border-radius: 1rem;
		background: #fff8e9;
		border: 1px solid #f5d98e;
		color: #7a4d12;
		font-size: 0.95rem;
		line-height: 1.7;
		box-shadow: 0 10px 25px rgba(122, 77, 18, 0.06);
	}

	.contact-card {
		margin-top: 1rem;
		padding: 1.25rem 1.25rem 1rem;
		border-radius: 1.35rem;
		background: #f7f6f2;
		border: 1px solid rgba(0, 0, 0, 0.08);
		box-shadow: 0 10px 25px rgba(16, 50, 74, 0.05);
	}

	.contact-card p {
		margin-bottom: 0.35rem;
	}

	@media (max-width: 768px) {
		.page {
			padding: 1rem;
		}

		.toc {
			display: none;
		}

		.content {
			max-width: 100%;
			padding: 0;
		}
	}
</style>