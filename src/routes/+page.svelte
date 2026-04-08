<script lang="ts">
	import type { ComponentType } from 'svelte';

	import {
		ArrowRight,
		Brain,
		CalendarDays,
		CheckCircle2,
		ChevronDown,
		ChevronRight,
		CircleCheckBig,
		ClipboardList,
		HeartPulse,
		Leaf,
		MapPinned,
		MessageSquareHeart,
		MoonStar,
		Phone,
		ShieldCheck,
		Sparkles,
		Users,
		Video
	} from 'lucide-svelte';

	type ServiceCard = {
		title: string;
		desc: string;
		icon: ComponentType;
	};

	type ConditionCard = {
		title: string;
		desc: string;
		tag: string;
	};

	const services: ServiceCard[] = [
		{
			title: 'Intellectual Conversations',
			desc: 'Engage in deep, structured discussions that help you explore ideas, emotions, and perspectives.',
			icon: Brain
		},
		{
			title: 'Compassionate Support',
			desc: 'A safe, judgment-free space where you can express yourself and receive thoughtful, empathetic responses.',
			icon: HeartPulse
		},
		{
			title: '24/7 AI Companion',
			desc: 'Always available whenever you need clarity, reflection, or meaningful conversation.',
			icon: MessageSquareHeart
		},
		{
			title: 'Self-Growth Tools',
			desc: 'Guided reflections and practical resources designed to help you understand yourself better.',
			icon: Leaf
		},
		{
			title: 'Stress & Clarity Support',
			desc: 'Navigate complex thoughts and emotions with structured conversational guidance.',
			icon: Sparkles
		},
		{
			title: 'Personalized Experience',
			desc: 'Adaptive conversations that evolve with your needs, context, and emotional state.',
			icon: Users
		}
	];

	const conditions: ConditionCard[] = [
		{
			title: 'Overthinking',
			desc: 'Break cycles of repetitive thoughts through guided, structured conversations.',
			tag: 'Challenge'
		},
		{
			title: 'Stress & Burnout',
			desc: 'Understand and manage pressure from work, studies, or daily life.',
			tag: 'Challenge'
		},
		{
			title: 'Lack of Clarity',
			desc: 'Gain perspective and direction when feeling mentally stuck or uncertain.',
			tag: 'Challenge'
		},
		{
			title: 'Loneliness',
			desc: 'Find a consistent companion to share thoughts and feel heard.',
			tag: 'Challenge'
		},
		{
			title: 'Emotional Confusion',
			desc: 'Untangle complex feelings and better understand your emotional state.',
			tag: 'Challenge'
		},
		{
			title: 'Self-Discovery',
			desc: 'Explore your identity, goals, and deeper thought patterns.',
			tag: 'Journey'
		}
	];

	const resources = [
		'All Resources',
		'Articles',
		'Conversation Guides',
		'Self-Assessments',
		'Growth Kits'
	];

	const trustBadges = [
		{ label: 'Private', sub: 'Conversations' },
		{ label: 'AI', sub: 'Driven' },
		{ label: '24/7', sub: 'Available' }
	];
</script>

<svelte:head>
	<title>Clarinth AI — AI Companion for Clarity and Growth</title>
	<meta
		name="description"
		content="Clarinth AI helps you explore thoughts, emotions, and self-growth through intelligent, compassionate conversations."
	/>
</svelte:head>

<div class="min-h-screen overflow-x-hidden bg-[#f7f6f2] text-[#18212b]">
	<main class="relative">
		<section class="relative overflow-hidden overflow-x-clip">
			<div class="pointer-events-none absolute inset-0">
				<div
					class="absolute top-14 -left-24 h-56 w-56 rounded-full bg-[#dcece7] blur-3xl sm:-left-32 sm:h-80 sm:w-80"
				></div>
				<div
					class="absolute top-20 right-0 h-64 w-64 rounded-full bg-[#e6ddd0] blur-3xl sm:h-96 sm:w-96"
				></div>
				<div
					class="absolute bottom-0 left-1/2 h-56 w-56 -translate-x-1/2 rounded-full bg-[#d7e2ec] blur-3xl sm:h-72 sm:w-72"
				></div>
			</div>

			<div
				class="relative mx-auto flex w-full flex-col gap-10 px-4 pt-8 pb-14 sm:px-6 sm:pt-10 lg:flex-row lg:items-start lg:px-8 lg:pt-14 lg:pb-24"
			>
				<div class="flex w-auto min-w-0 flex-col lg:flex-[1.08] lg:pt-10">
					<div
						class="mb-5 inline-flex w-auto md:w-min items-center gap-2 rounded-full border border-[#10324a]/10 bg-white px-4 py-2 text-sm text-slate-700 shadow-sm"
					>
						<Sparkles size={16} class="shrink-0 text-[#10324a]" />
						<span class="min-w-0 truncate"
							>For every thought, emotion, and moment of reflection</span
						>
					</div>

					<h1
						class="w-full text-3xl font-semibold tracking-tight text-[#12222f] sm:text-5xl lg:text-6xl"
					>
						A smarter way to understand your thoughts, emotions, and self
					</h1>

					<p class="mt-5 w-full text-base leading-7 text-slate-600 sm:mt-6 sm:text-lg sm:leading-8">
						Your AI companion for meaningful conversations, emotional clarity, and continuous
						self-growth—available whenever you need it.
					</p>

					<div class="mt-8 flex flex-col gap-3 sm:flex-row sm:gap-4">
						<a
							id="find-expert"
							href="#contact"
							class="inline-flex w-full items-center justify-center gap-2 rounded-full bg-[#10324a] px-6 py-3.5 text-sm font-semibold text-white shadow-lg shadow-[#10324a]/20 transition hover:translate-y-[-1px] hover:bg-[#0b2535] sm:w-auto"
						>
							Find clarity now <ArrowRight size={16} />
						</a>
						<a
							href="#services"
							class="inline-flex w-full items-center justify-center gap-2 rounded-full border border-slate-300 bg-white px-6 py-3.5 text-sm font-semibold text-slate-700 transition hover:border-[#10324a] hover:text-[#10324a] sm:w-auto"
						>
							Explore how it works <ChevronDown size={16} />
						</a>
					</div>

					<div class="mt-10 flex w-full flex-col gap-4 sm:flex-row sm:flex-wrap">
						<div
							class="w-full rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5 sm:flex-1 sm:basis-[16rem]"
						>
							<div class="flex items-start gap-3">
								<div
									class="flex h-11 w-11 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
								>
									<Video size={18} />
								</div>
								<div class="min-w-0">
									<div class="text-sm font-semibold">Intellectual Conversations</div>
									<div class="text-xs text-slate-500">Deep, thought-provoking dialogue</div>
								</div>
							</div>
						</div>

						<div
							class="w-full rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5 sm:flex-1 sm:basis-[16rem]"
						>
							<div class="flex items-start gap-3">
								<div
									class="flex h-11 w-11 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
								>
									<CalendarDays size={18} />
								</div>
								<div class="min-w-0">
									<div class="text-sm font-semibold">Compassionate Support</div>
									<div class="text-xs text-slate-500">Safe, judgment-free space</div>
								</div>
							</div>
						</div>

						<div
							class="w-full rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5 sm:flex-1 sm:basis-[16rem]"
						>
							<div class="flex items-start gap-3">
								<div
									class="flex h-11 w-11 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
								>
									<ShieldCheck size={18} />
								</div>
								<div class="min-w-0">
									<div class="text-sm font-semibold">Always Available</div>
									<div class="text-xs text-slate-500">24/7 AI companion</div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<div class="flex w-full min-w-0 flex-col lg:flex-[1.08] lg:pl-6">
					<div class="relative w-full">
						<div
							class="absolute top-5 left-3 h-full w-[calc(100%-0.75rem)] rounded-[2rem] border border-white/70 bg-white/60 shadow-[0_20px_70px_rgba(16,50,74,0.12)] backdrop-blur-sm sm:top-8 sm:left-0 sm:w-full"
						></div>

						<div
							class="relative overflow-hidden rounded-[2rem] bg-[#f0ede6] shadow-[0_20px_70px_rgba(16,50,74,0.12)] ring-1 ring-black/5"
						>
							<div class="flex flex-col gap-6 p-4 sm:p-6 xl:flex-row lg:gap-0 lg:p-8">
								<div
									class="overflow-hidden rounded-[1.75rem] bg-gradient-to-br from-[#dce8e2] via-[#efe9de] to-[#d9e1ea] lg:flex-[1.18]"
								>
									<div class="flex min-h-full flex-col justify-between p-5 sm:p-6 lg:p-8">
										<div>
											<div
												class="inline-flex items-center gap-2 rounded-full bg-white/80 px-3 py-1 text-xs font-medium text-slate-600"
											>
												<MoonStar size={14} />
												A calmer path to clarity
											</div>
											<h2
												class="mt-4 w-full text-2xl font-semibold tracking-tight text-[#12222f] sm:text-3xl"
											>
												Conversations that feel personal, structured, and grounded
											</h2>
											<p class="mt-3 w-full text-sm leading-6 text-slate-600 sm:text-[15px]">
												From uncertainty to insight, every step is designed to help you reflect,
												understand, and move forward with more confidence.
											</p>
										</div>

										<div class="mt-6 flex flex-col gap-3 sm:flex-row lg:flex-col! 3xl:flex-row!">
											<div class="flex-1 rounded-3xl bg-white/80 p-4 backdrop-blur">
												<div class="flex items-center gap-3">
													<div
														class="flex h-10 w-10 shrink-0 items-center justify-center rounded-2xl bg-[#10324a] text-white"
													>
														<CircleCheckBig size={16} />
													</div>
													<div class="min-w-0">
														<div class="text-sm font-semibold">Guided thinking</div>
														<div class="text-xs text-slate-500">
															Reflection and structured insight
														</div>
													</div>
												</div>
											</div>

											<div class="flex-1 rounded-3xl bg-white/80 p-4 backdrop-blur">
												<div class="flex items-center gap-3">
													<div
														class="flex h-10 w-10 shrink-0 items-center justify-center rounded-2xl bg-[#10324a] text-white"
													>
														<MapPinned size={16} />
													</div>
													<div class="min-w-0">
														<div class="text-sm font-semibold">Always accessible</div>
														<div class="text-xs text-slate-500">Anytime, anywhere support</div>
													</div>
												</div>
											</div>
										</div>
									</div>
								</div>

								<div
									class="relative flex w-full justify-center bg-white/35 p-4 lg:flex-[0.82] lg:items-end"
								>
									<div
										class="relative w-full rounded-[2rem] bg-[#10324a] p-4 text-white shadow-2xl"
									>
										<div
											class="absolute top-4 left-1/2 h-1 w-12 -translate-x-1/2 rounded-full bg-white/30"
										></div>

										<div class="mt-8 rounded-[1.6rem] bg-white/10 p-4 backdrop-blur">
											<div class="flex items-center justify-between gap-3">
												<div class="text-xs tracking-[0.2em] text-white/70 uppercase">Today</div>
												<ShieldCheck size={16} class="shrink-0 text-white/70" />
											</div>

											<div class="mt-3 text-lg font-semibold">Your care journey</div>

											<div class="mt-3 space-y-3">
												<div class="flex items-center gap-3 rounded-2xl bg-white/10 px-3 py-2">
													<div
														class="flex h-8 w-8 shrink-0 items-center justify-center rounded-xl bg-white text-[#10324a]"
													>
														<ClipboardList size={15} />
													</div>
													<div class="text-sm">Reflection</div>
												</div>
												<div class="flex items-center gap-3 rounded-2xl bg-white/10 px-3 py-2">
													<div
														class="flex h-8 w-8 shrink-0 items-center justify-center rounded-xl bg-white text-[#10324a]"
													>
														<MessageSquareHeart size={15} />
													</div>
													<div class="text-sm">Conversation</div>
												</div>
												<div class="flex items-center gap-3 rounded-2xl bg-white/10 px-3 py-2">
													<div
														class="flex h-8 w-8 shrink-0 items-center justify-center rounded-xl bg-white text-[#10324a]"
													>
														<CheckCircle2 size={15} />
													</div>
													<div class="text-sm">Clarity</div>
												</div>
											</div>
										</div>
									</div>
								</div>
							</div>

							<div class="flex flex-col gap-3 p-4 sm:flex-row sm:flex-wrap sm:p-6 lg:p-8">
								{#each trustBadges as badge}
									<div
										class="w-full rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5 sm:flex-1 sm:basis-[10rem]"
									>
										<div class="text-sm font-semibold text-[#10324a]">{badge.label}</div>
										<div class="text-xs text-slate-500">{badge.sub}</div>
									</div>
								{/each}
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>

		<section id="experts" class="mx-auto max-w-7xl px-4 pb-8 sm:px-6 lg:px-8">
			<div class="grid gap-6 lg:grid-cols-12">
				<div class="lg:col-span-4">
					<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5 sm:p-7">
						<div
							class="inline-flex items-center gap-2 rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase"
						>
							Use Cases
						</div>
						<h2 class="mt-4 text-2xl font-semibold tracking-tight sm:text-3xl">
							Choose the right path for the moment you are in.
						</h2>
						<p class="mt-3 text-sm leading-7 text-slate-600">
							A clear way to explore intellectual conversation, emotional support, and guided
							self-reflection.
						</p>
						<a
							href="#contact"
							class="mt-5 inline-flex items-center gap-2 text-sm font-semibold text-[#10324a]"
						>
							Start a conversation <ArrowRight size={16} />
						</a>
					</div>
				</div>

				<div class="lg:col-span-8">
					<div class="grid gap-4 md:grid-cols-2">
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
								>
									<Users size={20} />
								</div>
								<div class="min-w-0">
									<div class="font-semibold">Intellectual Conversations</div>
									<div class="text-sm text-slate-500">Deep, thoughtful dialogue</div>
								</div>
							</div>
						</div>
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
								>
									<HeartPulse size={20} />
								</div>
								<div class="min-w-0">
									<div class="font-semibold">Compassionate Support</div>
									<div class="text-sm text-slate-500">Empathetic and judgment-free interaction</div>
								</div>
							</div>
						</div>
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
								>
									<Sparkles size={20} />
								</div>
								<div class="min-w-0">
									<div class="font-semibold">Thought Exploration</div>
									<div class="text-sm text-slate-500">Explore ideas, beliefs, and patterns</div>
								</div>
							</div>
						</div>
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
								>
									<Users size={20} />
								</div>
								<div class="min-w-0">
									<div class="font-semibold">Personal Growth</div>
									<div class="text-sm text-slate-500">Continuous self-improvement</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>

		<section id="services" class="mx-auto max-w-7xl px-4 py-10 sm:px-6 sm:py-12 lg:px-8">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<div>
					<div
						class="inline-flex items-center gap-2 rounded-full bg-white px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase shadow-sm ring-1 ring-black/5"
					>
						Services
					</div>
					<h2 class="mt-4 text-2xl font-semibold tracking-tight sm:text-3xl">
						A complete AI-powered mental clarity system.
					</h2>
				</div>
				<p class="max-w-2xl text-sm leading-7 text-slate-600">
					Move from confusion to clarity through structured conversations and intelligent
					reflection.
				</p>
			</div>

			<div class="mt-8 grid gap-4 md:grid-cols-2 xl:grid-cols-3">
				{#each services as service}
					<article
						class="group rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5 transition hover:-translate-y-0.5 hover:shadow-md"
					>
						<div
							class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#10324a] text-white shadow-sm"
						>
							<svelte:component this={service.icon} size={20} />
						</div>
						<h3 class="mt-5 text-xl font-semibold tracking-tight">{service.title}</h3>
						<p class="mt-3 text-sm leading-7 text-slate-600">{service.desc}</p>
						<div class="mt-5 inline-flex items-center gap-2 text-sm font-semibold text-[#10324a]">
							Learn more <ChevronRight size={16} class="transition group-hover:translate-x-0.5" />
						</div>
					</article>
				{/each}
			</div>
		</section>

		<section id="centres" class="mx-auto max-w-7xl px-4 py-10 sm:px-6 sm:py-12 lg:px-8">
			<div class="grid gap-6 lg:grid-cols-12">
				<div class="lg:col-span-5">
					<div class="rounded-[2rem] bg-[#10324a] p-6 text-white shadow-lg sm:p-8">
						<div
							class="inline-flex items-center gap-2 rounded-full bg-white/10 px-3 py-1 text-xs font-semibold tracking-[0.22em] text-white/80 uppercase"
						>
							Availability
						</div>
						<h2 class="mt-4 text-2xl font-semibold tracking-tight sm:text-3xl">
							Accessible anywhere, anytime.
						</h2>
						<p class="mt-3 text-sm leading-7 text-white/80">
							No physical boundaries—your AI companion is always within reach.
						</p>
						<div class="mt-6 grid gap-3 sm:grid-cols-3">
							<div class="rounded-3xl bg-white/10 p-4">
								<div class="text-sm font-semibold">Global access</div>
								<div class="text-xs text-white/70">Digital-first experience</div>
							</div>
							<div class="rounded-3xl bg-white/10 p-4">
								<div class="text-sm font-semibold">Always online</div>
								<div class="text-xs text-white/70">No scheduling needed</div>
							</div>
							<div class="rounded-3xl bg-white/10 p-4">
								<div class="text-sm font-semibold">Instant support</div>
								<div class="text-xs text-white/70">Start anytime</div>
							</div>
						</div>
					</div>
				</div>

				<div class="lg:col-span-7">
					<div class="grid gap-4 md:grid-cols-2">
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
								>
									<MapPinned size={20} />
								</div>
								<div class="min-w-0">
									<div class="font-semibold">Private by design</div>
									<div class="text-sm text-slate-500">Thoughtful, secure interaction</div>
								</div>
							</div>
						</div>
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]"
								>
									<Phone size={20} />
								</div>
								<div class="min-w-0">
									<div class="font-semibold">Reach out anytime</div>
									<div class="text-sm text-slate-500">Support for questions and next steps</div>
								</div>
							</div>
						</div>
						<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5 md:col-span-2">
							<div class="flex flex-col gap-6 md:flex-row md:items-center md:justify-between">
								<div class="min-w-0">
									<div class="text-sm font-semibold tracking-[0.22em] text-[#10324a] uppercase">
										Contact
									</div>
									<h3 id="contact" class="mt-2 text-2xl font-semibold tracking-tight">
										Need help deciding where to start?
									</h3>
									<p class="mt-2 max-w-2xl text-sm leading-7 text-slate-600">
										Explore how Clarinth AI can support your thinking, emotions, and personal growth
										journey.
									</p>
								</div>
								<div class="flex flex-col gap-3 sm:flex-row md:flex-shrink-0">
									<a
										href="mailto:hello@example.com"
										class="inline-flex items-center justify-center gap-2 rounded-full border border-slate-300 bg-white px-5 py-3 text-sm font-semibold text-slate-700 transition hover:border-[#10324a] hover:text-[#10324a]"
									>
										Email support
									</a>
									<a
										href="#find-expert"
										class="inline-flex items-center justify-center gap-2 rounded-full bg-[#10324a] px-5 py-3 text-sm font-semibold text-white shadow-sm"
									>
										Start now <ArrowRight size={16} />
									</a>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>

		<section id="resources" class="mx-auto max-w-7xl px-4 py-10 sm:px-6 sm:py-12 lg:px-8">
			<div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5 sm:p-8">
				<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
					<div>
						<div
							class="inline-flex items-center gap-2 rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase"
						>
							Resources
						</div>
						<h2 class="mt-4 text-2xl font-semibold tracking-tight sm:text-3xl">
							Guided conversations, tools, and insights.
						</h2>
					</div>
					<p class="max-w-2xl text-sm leading-7 text-slate-600">
						A growing library of resources to support your mental clarity and self-development.
					</p>
				</div>

				<div class="mt-6 flex flex-wrap gap-3">
					{#each resources as resource}
						<span
							class="rounded-full border border-slate-200 bg-slate-50 px-4 py-2 text-sm font-medium text-slate-700"
						>
							{resource}
						</span>
					{/each}
				</div>
			</div>
		</section>

		<section id="conditions" class="mx-auto max-w-7xl px-4 py-10 sm:px-6 sm:py-12 lg:px-8">
			<div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
				<div>
					<div
						class="inline-flex items-center gap-2 rounded-full bg-white px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase shadow-sm ring-1 ring-black/5"
					>
						Challenges
					</div>
					<h2 class="mt-4 text-2xl font-semibold tracking-tight sm:text-3xl">
						Common challenges, clearly addressed.
					</h2>
				</div>
				<p class="max-w-2xl text-sm leading-7 text-slate-600">
					Identify what you are experiencing and explore the right conversational path forward.
				</p>
			</div>

			<div class="mt-8 grid gap-4 md:grid-cols-2 xl:grid-cols-3">
				{#each conditions as item}
					<article class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
						<div
							class="inline-flex rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-semibold tracking-[0.2em] text-[#10324a] uppercase"
						>
							{item.tag}
						</div>
						<h3 class="mt-4 text-xl font-semibold tracking-tight">{item.title}</h3>
						<p class="mt-3 text-sm leading-7 text-slate-600">{item.desc}</p>
					</article>
				{/each}
			</div>
		</section>

		<section class="mx-auto max-w-7xl px-4 py-10 sm:px-6 sm:py-12 lg:px-8">
			<div class="rounded-[2rem] bg-[#edf2f4] p-6 sm:p-8">
				<div class="grid gap-8 lg:grid-cols-12 lg:items-center">
					<div class="lg:col-span-7">
						<div
							class="inline-flex items-center gap-2 rounded-full bg-white px-3 py-1 text-xs font-semibold tracking-[0.22em] text-[#10324a] uppercase shadow-sm ring-1 ring-black/5"
						>
							App
						</div>
						<h2 class="mt-4 text-2xl font-semibold tracking-tight text-[#12222f] sm:text-3xl">
							Keep clarity within reach.
						</h2>
						<p class="mt-3 max-w-2xl text-sm leading-7 text-slate-600">
							Access your AI companion anytime and continue your journey of reflection and growth.
						</p>
					</div>
					<div class="lg:col-span-5">
						<div class="rounded-[2rem] bg-white p-5 shadow-sm ring-1 ring-black/5 sm:p-6">
							<div class="flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between">
								<div>
									<div class="text-sm font-semibold">Download the app</div>
									<div class="text-xs text-slate-500">Simplify your experience</div>
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
									App Store <ArrowRight size={16} />
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
