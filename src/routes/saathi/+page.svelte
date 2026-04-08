<script lang="ts">
	import {
		ArrowRight,
		Brain,
		CheckCircle2,
		ChevronDown,
		Clock3,
		HeartPulse,
		Leaf,
		MessageSquareHeart,
		Phone,
		ShieldCheck,
		Sparkles,
		Users
	} from 'lucide-svelte';

	let activeIndex: number | null = null;

	const faqs = [
		{
			q: 'Is Saathi a replacement for therapy?',
			a: "Saathi complements professional therapy but isn't a replacement for severe mental health conditions. Think of it as a therapist-guided self-help tool available 24/7."
		},
		{
			q: 'How is this different from a chatbot?',
			a: 'Saathi uses structured CBT frameworks with adaptive intelligence. It understands context, evolves with you, and delivers evidence-based therapy—not generic responses.'
		},
		{
			q: 'Is my data private?',
			a: 'Yes. All conversations are end-to-end encrypted. Your data is never sold or shared with third parties.'
		},
		{
			q: 'What if I need crisis support?',
			a: 'Saathi is not for crisis intervention. If you are in immediate danger, please contact local emergency services or a crisis helpline.'
		},
		{
			q: 'Can I use Saathi with my therapist?',
			a: 'Absolutely. Many users use Saathi between sessions to reinforce techniques and track progress.'
		}
	];

	function toggle(index: number) {
		activeIndex = activeIndex === index ? null : index;
	}
</script>

<svelte:head>
	<title>Saathi — Mental Clarity | Clarinth.AI</title>
	<meta
		name="description"
		content="Saathi is Clarinth.AI’s mental wellbeing companion that helps you navigate anxiety, stress, and emotional complexity with clarity."
	/>
</svelte:head>

<div class="min-h-screen overflow-x-clip bg-[#f7f6f2] text-[#18212b]">
	<main>
		<!-- HERO -->
		<section class="relative overflow-hidden bg-[#f7f6f2]">
			<div class="pointer-events-none absolute inset-0">
				<div
					class="absolute -top-24 -left-24 h-72 w-72 rounded-full bg-[#dcece7] blur-3xl sm:h-96 sm:w-96"
				></div>
				<div
					class="absolute top-16 right-0 h-80 w-80 rounded-full bg-[#e6ddd0] blur-3xl sm:h-[28rem] sm:w-[28rem]"
				></div>
				<div
					class="absolute bottom-0 left-1/2 h-72 w-72 -translate-x-1/2 rounded-full bg-[#d7e2ec] blur-3xl sm:h-96 sm:w-96"
				></div>
			</div>

			<div
				class="relative mx-auto max-w-7xl px-4 pt-10 pb-14 sm:px-6 sm:pt-14 lg:px-8 lg:pt-16 lg:pb-24"
			>
				<div class="grid items-center gap-10 lg:grid-cols-[1.08fr_0.92fr]">
					<div class="min-w-0">
						<div
							class="inline-flex items-center gap-2 rounded-full border border-[#10324a]/10 bg-white px-4 py-2 text-xs font-semibold tracking-[0.24em] text-[#10324a] uppercase shadow-sm"
						>
							<Sparkles size={14} class="shrink-0" />
							Mental wellbeing companion
						</div>

						<h1
							class="mt-5 max-w-3xl text-4xl font-semibold tracking-tight text-[#12222f] sm:text-5xl lg:text-6xl"
						>
							Saathi brings calm, clarity, and support to your mental wellness journey.
						</h1>

						<p class="mt-5 max-w-2xl text-base leading-7 text-slate-600 sm:text-lg sm:leading-8">
							Evidence-based support that understands you. Saathi helps you reflect, manage stress,
							and move forward with structured guidance that feels personal, private, and always
							accessible.
						</p>

						<div class="mt-8 flex flex-col gap-3 sm:flex-row sm:gap-4">
							<a
								href="#pricing"
								class="inline-flex w-full items-center justify-center gap-2 rounded-full bg-[#10324a] px-6 py-3.5 text-sm font-semibold text-white shadow-lg shadow-[#10324a]/15 transition hover:-translate-y-0.5 hover:bg-[#0b2535] sm:w-auto"
							>
								Start Your Journey <ArrowRight size={16} />
							</a>
							<a
								href="#how-it-works"
								class="inline-flex w-full items-center justify-center gap-2 rounded-full border border-slate-300 bg-white px-6 py-3.5 text-sm font-semibold text-slate-700 transition hover:border-[#10324a] hover:text-[#10324a] sm:w-auto"
							>
								See How It Works <ChevronDown size={16} />
							</a>
						</div>

						<div class="mt-10 grid gap-4 sm:grid-cols-3">
							<div class="rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5">
								<div class="flex items-start gap-3">
									<div
										class="flex h-11 w-11 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
									>
										<Brain size={18} />
									</div>
									<div class="min-w-0">
										<div class="text-sm font-semibold text-[#12222f]">Structured support</div>
										<div class="text-xs text-slate-500">Guided, thoughtful conversations</div>
									</div>
								</div>
							</div>

							<div class="rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5">
								<div class="flex items-start gap-3">
									<div
										class="flex h-11 w-11 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
									>
										<Clock3 size={18} />
									</div>
									<div class="min-w-0">
										<div class="text-sm font-semibold text-[#12222f]">Always available</div>
										<div class="text-xs text-slate-500">Support when you need it</div>
									</div>
								</div>
							</div>

							<div class="rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5">
								<div class="flex items-start gap-3">
									<div
										class="flex h-11 w-11 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
									>
										<ShieldCheck size={18} />
									</div>
									<div class="min-w-0">
										<div class="text-sm font-semibold text-[#12222f]">Private by design</div>
										<div class="text-xs text-slate-500">Protected, secure, and trusted</div>
									</div>
								</div>
							</div>
						</div>
					</div>

					<div class="relative">
						<div class="absolute -top-6 right-10 h-24 w-24 rounded-full bg-white/50 blur-2xl"></div>
						<div
							class="absolute -bottom-6 left-6 h-24 w-24 rounded-full bg-white/50 blur-2xl"
						></div>

						<div
							class="relative overflow-hidden rounded-[2rem] bg-white p-5 shadow-[0_18px_70px_rgba(16,50,74,0.12)] ring-1 ring-black/5 sm:p-6"
						>
							<div class="flex items-center justify-between gap-4 border-b border-slate-100 pb-4">
								<div class="flex items-center gap-3">
									<div
										class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#10324a] text-white shadow-sm"
									>
										<MessageSquareHeart size={18} />
									</div>
									<div>
										<div class="text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase">
											Saathi
										</div>
										<div class="mt-1 text-lg font-semibold text-[#12222f]">Your safe space</div>
									</div>
								</div>
								<div class="rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-medium text-[#10324a]">
									24/7 active
								</div>
							</div>

							<div class="mt-5 grid gap-3">
								<div class="rounded-2xl bg-[#f4f6f8] p-4">
									<div class="text-sm font-semibold text-[#12222f]">Guided reflection</div>
									<p class="mt-1 text-sm leading-6 text-slate-600">
										Structured conversations that help you understand what you are feeling.
									</p>
								</div>

								<div class="rounded-2xl bg-[#f4f6f8] p-4">
									<div class="text-sm font-semibold text-[#12222f]">Privacy first</div>
									<p class="mt-1 text-sm leading-6 text-slate-600">
										Designed to keep your data protected and your experience secure.
									</p>
								</div>
							</div>

							<div class="mt-5 rounded-[1.75rem] bg-[#10324a] p-4 text-white">
								<div class="text-xs tracking-[0.24em] text-white/60 uppercase">
									Conversation preview
								</div>

								<div class="mt-4 space-y-3">
									<div
										class="max-w-[88%] rounded-3xl rounded-bl-md bg-white/10 px-4 py-3 text-sm leading-6 text-white/90"
									>
										I have been feeling overwhelmed and I need a place to slow down.
									</div>

									<div
										class="ml-auto max-w-[88%] rounded-3xl rounded-br-md bg-white px-4 py-3 text-sm leading-6 text-[#10324a]"
									>
										Let’s work through it step by step.
									</div>
								</div>
							</div>

							<div class="mt-5 grid gap-3 sm:grid-cols-3">
								<div class="rounded-2xl bg-[#f8f9fa] p-3 text-center">
									<div class="text-sm font-semibold text-[#10324a]">Private</div>
									<div class="text-xs text-slate-500">Conversations</div>
								</div>
								<div class="rounded-2xl bg-[#f8f9fa] p-3 text-center">
									<div class="text-sm font-semibold text-[#10324a]">CBT</div>
									<div class="text-xs text-slate-500">Structured</div>
								</div>
								<div class="rounded-2xl bg-[#f8f9fa] p-3 text-center">
									<div class="text-sm font-semibold text-[#10324a]">24/7</div>
									<div class="text-xs text-slate-500">Available</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>

		<!-- PROBLEM -->
		<section class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
			<div class="grid gap-6 lg:grid-cols-12">
				<div class="lg:col-span-4">
					<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
						<div
							class="inline-flex items-center gap-2 rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase"
						>
							The problem
						</div>
						<h2 class="mt-4 text-2xl font-semibold tracking-tight">
							Mental health should not feel complicated.
						</h2>
						<p class="mt-3 text-sm leading-7 text-slate-600">
							When anxiety, stress, or low mood pile up, simple support can feel out of reach.
							Saathi is built to make support feel clear, private, and usable.
						</p>
					</div>
				</div>

				<div class="lg:col-span-8">
					<div class="grid gap-4 md:grid-cols-3">
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
							<div
								class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
							>
								<HeartPulse size={20} />
							</div>
							<div class="mt-4 font-semibold">Overwhelmed by symptoms</div>
							<p class="mt-2 text-sm text-slate-600">
								Anxiety, stress, and low mood can make every day feel heavier than it should.
							</p>
						</div>
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
							<div
								class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
							>
								<Users size={20} />
							</div>
							<div class="mt-4 font-semibold">Generic tools</div>
							<p class="mt-2 text-sm text-slate-600">
								Many apps are broad, impersonal, and hard to stick with.
							</p>
						</div>
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
							<div
								class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
							>
								<Leaf size={20} />
							</div>
							<div class="mt-4 font-semibold">Need for clarity</div>
							<p class="mt-2 text-sm text-slate-600">
								What people often need is not more noise, but structured understanding.
							</p>
						</div>
					</div>
				</div>
			</div>
		</section>

		<!-- DIFFERENCE -->
		<section class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<div>
					<div
						class="inline-flex items-center gap-2 rounded-full bg-white px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase shadow-sm ring-1 ring-black/5"
					>
						Saathi difference
					</div>
					<h2 class="mt-4 text-3xl font-semibold tracking-tight">
						Clarity in your mental health journey.
					</h2>
				</div>
				<p class="max-w-2xl text-sm leading-7 text-slate-600">
					Saathi combines personalized support, clinically informed methods, and always-available
					guidance into one calm experience.
				</p>
			</div>

			<div class="mt-8 grid gap-4 md:grid-cols-3">
				<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
					<div
						class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
					>
						<Brain size={20} />
					</div>
					<h3 class="mt-5 text-xl font-semibold tracking-tight">Personalized to you</h3>
					<p class="mt-3 text-sm leading-7 text-slate-600">
						Saathi learns your story, triggers, and preferences so support fits your situation.
					</p>
				</div>
				<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
					<div
						class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
					>
						<Sparkles size={20} />
					</div>
					<h3 class="mt-5 text-xl font-semibold tracking-tight">Clinically informed</h3>
					<p class="mt-3 text-sm leading-7 text-slate-600">
						Built on CBT-style structure so guidance feels practical and grounded.
					</p>
				</div>
				<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
					<div
						class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
					>
						<Phone size={20} />
					</div>
					<h3 class="mt-5 text-xl font-semibold tracking-tight">Available when needed</h3>
					<p class="mt-3 text-sm leading-7 text-slate-600">
						No appointments or waiting rooms. Use Saathi when a clear next step matters most.
					</p>
				</div>
			</div>
		</section>

		<!-- HOW IT WORKS -->
		<section id="how-it-works" class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<div>
					<div
						class="inline-flex items-center gap-2 rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase"
					>
						How it works
					</div>
					<h2 class="mt-4 text-3xl font-semibold tracking-tight">
						From chaos to clarity in four steps.
					</h2>
				</div>
				<p class="max-w-2xl text-sm leading-7 text-slate-600">
					A calm, structured flow that helps Saathi understand you, shape support, and track
					progress.
				</p>
			</div>

			<div class="mt-8 grid gap-4 md:grid-cols-2 xl:grid-cols-4">
				<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
					<div class="text-sm font-semibold tracking-[0.2em] text-[#10324a] uppercase">01</div>
					<h3 class="mt-4 text-xl font-semibold tracking-tight">We understand you</h3>
					<p class="mt-3 text-sm leading-7 text-slate-600">
						Share what is going on in your own words. Saathi listens and identifies the main
						patterns.
					</p>
				</div>
				<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
					<div class="text-sm font-semibold tracking-[0.2em] text-[#10324a] uppercase">02</div>
					<h3 class="mt-4 text-xl font-semibold tracking-tight">We create your path</h3>
					<p class="mt-3 text-sm leading-7 text-slate-600">
						Saathi shapes a personalized therapy journey around your goals and needs.
					</p>
				</div>
				<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
					<div class="text-sm font-semibold tracking-[0.2em] text-[#10324a] uppercase">03</div>
					<h3 class="mt-4 text-xl font-semibold tracking-tight">We guide your progress</h3>
					<p class="mt-3 text-sm leading-7 text-slate-600">
						The plan adapts as you respond, so the experience stays relevant and useful.
					</p>
				</div>
				<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
					<div class="text-sm font-semibold tracking-[0.2em] text-[#10324a] uppercase">04</div>
					<h3 class="mt-4 text-xl font-semibold tracking-tight">We celebrate growth</h3>
					<p class="mt-3 text-sm leading-7 text-slate-600">
						Track improvements with progress markers, reflections, and validated assessments.
					</p>
				</div>
			</div>
		</section>

		<!-- FEATURES -->
		<section class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
			<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5 sm:p-8">
				<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
					<div>
						<div
							class="inline-flex items-center gap-2 rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase"
						>
							What you get
						</div>
						<h2 class="mt-4 text-3xl font-semibold tracking-tight">
							Everything you need for mental clarity.
						</h2>
					</div>
					<p class="max-w-2xl text-sm leading-7 text-slate-600">
						Built for steady progress, privacy, and accessibility across real-life situations.
					</p>
				</div>

				<div class="mt-6 grid gap-3 sm:grid-cols-2 xl:grid-cols-3">
					<div
						class="rounded-full border border-slate-200 bg-slate-50 px-4 py-3 text-sm font-medium text-slate-700"
					>
						Personalized CBT therapy
					</div>
					<div
						class="rounded-full border border-slate-200 bg-slate-50 px-4 py-3 text-sm font-medium text-slate-700"
					>
						24/7 availability
					</div>
					<div
						class="rounded-full border border-slate-200 bg-slate-50 px-4 py-3 text-sm font-medium text-slate-700"
					>
						Evidence-based methods
					</div>
					<div
						class="rounded-full border border-slate-200 bg-slate-50 px-4 py-3 text-sm font-medium text-slate-700"
					>
						Progress tracking
					</div>
					<div
						class="rounded-full border border-slate-200 bg-slate-50 px-4 py-3 text-sm font-medium text-slate-700"
					>
						Privacy first
					</div>
					<div
						class="rounded-full border border-slate-200 bg-slate-50 px-4 py-3 text-sm font-medium text-slate-700"
					>
						Affordable access
					</div>
				</div>
			</div>
		</section>

		<!-- PRICING -->
		<section id="pricing" class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<div>
					<div
						class="inline-flex items-center gap-2 rounded-full bg-white px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase shadow-sm ring-1 ring-black/5"
					>
						Pricing
					</div>
					<h2 class="mt-4 text-3xl font-semibold tracking-tight">
						Accessible mental health for everyone.
					</h2>
				</div>
				<p class="max-w-2xl text-sm leading-7 text-slate-600">
					Choose a plan that fits how you want to begin, continue, or scale Saathi across your
					organization.
				</p>
			</div>

			<div class="mt-8 grid gap-4 md:grid-cols-3">
				<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
					<div class="text-sm font-semibold text-[#10324a]">Monthly</div>
					<div class="mt-3 text-3xl font-semibold tracking-tight">₹999</div>
					<div class="mt-1 text-sm text-slate-500">per month</div>
					<ul class="mt-5 space-y-2 text-sm text-slate-600">
						<li class="flex gap-2">
							<CheckCircle2 size={16} class="mt-0.5 shrink-0 text-[#10324a]" /> Full access to Saathi
						</li>
						<li class="flex gap-2">
							<CheckCircle2 size={16} class="mt-0.5 shrink-0 text-[#10324a]" /> Personalized CBT modules
						</li>
						<li class="flex gap-2">
							<CheckCircle2 size={16} class="mt-0.5 shrink-0 text-[#10324a]" /> Progress tracking
						</li>
					</ul>
					<button
						class="mt-6 inline-flex w-full items-center justify-center rounded-full bg-[#10324a] px-5 py-3 text-sm font-semibold text-white transition hover:bg-[#0b2535]"
					>
						Start Free Trial
					</button>
				</div>

				<div class="rounded-[2rem] bg-[#10324a] p-6 text-white shadow-sm ring-1 ring-black/5">
					<div class="text-sm font-semibold text-white/80">Annual</div>
					<div class="mt-3 text-3xl font-semibold tracking-tight">₹9,990</div>
					<div class="mt-1 text-sm text-white/70">Save ₹2,000</div>
					<ul class="mt-5 space-y-2 text-sm text-white/80">
						<li class="flex gap-2">
							<CheckCircle2 size={16} class="mt-0.5 shrink-0 text-white" /> Everything in Monthly
						</li>
						<li class="flex gap-2">
							<CheckCircle2 size={16} class="mt-0.5 shrink-0 text-white" /> Priority support
						</li>
						<li class="flex gap-2">
							<CheckCircle2 size={16} class="mt-0.5 shrink-0 text-white" /> Extended progress reports
						</li>
					</ul>
					<button
						class="mt-6 inline-flex w-full items-center justify-center rounded-full bg-white px-5 py-3 text-sm font-semibold text-[#10324a] transition hover:bg-white/90"
					>
						Start Free Trial
					</button>
				</div>

				<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
					<div class="text-sm font-semibold text-[#10324a]">Enterprise</div>
					<div class="mt-3 text-3xl font-semibold tracking-tight">Custom</div>
					<div class="mt-1 text-sm text-slate-500">For organizations</div>
					<ul class="mt-5 space-y-2 text-sm text-slate-600">
						<li class="flex gap-2">
							<CheckCircle2 size={16} class="mt-0.5 shrink-0 text-[#10324a]" /> Unlimited team members
						</li>
						<li class="flex gap-2">
							<CheckCircle2 size={16} class="mt-0.5 shrink-0 text-[#10324a]" /> Admin dashboard
						</li>
						<li class="flex gap-2">
							<CheckCircle2 size={16} class="mt-0.5 shrink-0 text-[#10324a]" /> Aggregated insights
						</li>
					</ul>
					<button
						class="mt-6 inline-flex w-full items-center justify-center rounded-full border border-slate-300 px-5 py-3 text-sm font-semibold text-slate-700 transition hover:border-[#10324a] hover:text-[#10324a]"
					>
						Contact Sales
					</button>
				</div>
			</div>
		</section>

		<!-- FAQ -->
		<section class="bg-white py-16">
			<div class="mx-auto max-w-3xl px-6">
				<h2 class="mb-8 text-2xl font-semibold text-gray-900 md:text-3xl">Common Questions</h2>

				<div class="space-y-3">
					{#each faqs as faq, i}
						<div class="overflow-hidden rounded-xl border border-gray-200">
							<button
								class="flex w-full items-center justify-between px-5 py-4 text-left text-sm font-medium text-gray-900 transition hover:bg-gray-50 md:text-base"
								on:click={() => toggle(i)}
							>
								<span>{faq.q}</span>

								<ChevronDown
									size={18}
									class={`transition-transform duration-200 ${
										activeIndex === i ? 'rotate-180' : ''
									}`}
								/>
							</button>

							<div
								class={`grid transition-all duration-300 ease-in-out ${
									activeIndex === i ? 'grid-rows-[1fr] opacity-100' : 'grid-rows-[0fr] opacity-0'
								}`}
							>
								<div class="overflow-hidden">
									<p class="px-5 pb-4 text-sm leading-relaxed text-gray-600">
										{faq.a}
									</p>
								</div>
							</div>
						</div>
					{/each}
				</div>
			</div>
		</section>

		<!-- FINAL CTA -->
		<section class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8 lg:pb-20">
			<div class="rounded-[2rem] bg-[#edf2f4] p-6 sm:p-8">
				<div class="grid gap-8 lg:grid-cols-12 lg:items-center">
					<div class="lg:col-span-7">
						<div
							class="inline-flex items-center gap-2 rounded-full bg-white px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase shadow-sm ring-1 ring-black/5"
						>
							Get started
						</div>
						<h2 class="mt-4 text-3xl font-semibold tracking-tight text-[#12222f]">
							Start your journey to mental clarity.
						</h2>
						<p class="mt-3 max-w-2xl text-sm leading-7 text-slate-600">
							Join thousands who’ve found understanding, relief, and growth with Saathi.
						</p>
					</div>
					<div class="lg:col-span-5">
						<div class="rounded-[2rem] bg-white p-5 shadow-sm ring-1 ring-black/5">
							<div class="flex items-center justify-between gap-4">
								<div>
									<div class="text-sm font-semibold">14-day free trial</div>
									<div class="text-xs text-slate-500">No credit card required</div>
								</div>
								<div
									class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#10324a] text-white"
								>
									<Phone size={18} />
								</div>
							</div>
							<div class="mt-4 flex flex-col gap-3 sm:flex-row">
								<button
									class="inline-flex w-full items-center justify-center gap-2 rounded-full bg-[#10324a] px-5 py-3 text-sm font-semibold text-white sm:w-auto"
								>
									Begin Your Journey <ArrowRight size={16} />
								</button>
								<button
									class="inline-flex w-full items-center justify-center gap-2 rounded-full border border-slate-300 px-5 py-3 text-sm font-semibold text-slate-700 sm:w-auto"
								>
									Learn more
								</button>
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>
	</main>
</div>
