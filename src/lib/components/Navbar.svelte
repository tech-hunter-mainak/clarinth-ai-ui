<script lang="ts">
	import { onMount } from 'svelte';
	import {
		ArrowRight,
		ChevronDown,
		ChevronRight,
		Menu,
		MessageSquareHeart,
		X
	} from 'lucide-svelte';

	type NavItem = {
		label: string;
		href?: string;
		children?: { label: string; href: string }[];
	};

	const navItems: NavItem[] = [
		{
			label: 'Product',
			children: [
				{ label: 'AI Companion', href: '#' },
				{ label: 'Conversations', href: '#' },
				{ label: 'Emotional Support', href: '#' },
				{ label: 'Self-Growth Tools', href: '#' }
			]
		},
		{
			label: 'Features',
			children: [
				{ label: 'Intellectual Discussions', href: '#' },
				{ label: 'Guided Reflection', href: '#' },
				{ label: 'Emotional Clarity', href: '#' },
				{ label: 'Personalized Experience', href: '#' }
			]
		},
		{
			label: 'Use Cases',
			children: [
				{ label: 'Students', href: '#' },
				{ label: 'Professionals', href: '#' },
				{ label: 'Self Growth', href: '#' }
			]
		},
		{
			label: 'Resources',
			children: [
				{ label: 'Articles', href: '#' },
				{ label: 'Guides', href: '#' },
				{ label: 'Assessments', href: '#' }
			]
		},
		{
			label: 'Challenges',
			children: [
				{ label: 'Overthinking', href: '#' },
				{ label: 'Stress & Burnout', href: '#' },
				{ label: 'Lack of Clarity', href: '#' }
			]
		}
	];

	let mobileMenuOpen = false;
	let activeDropdown: string | null = null;

	function toggleDropdown(label: string) {
		activeDropdown = activeDropdown === label ? null : label;
	}

	function openMobileMenu() {
		mobileMenuOpen = true;
		activeDropdown = null;
		if (typeof document !== 'undefined') {
			document.body.style.overflow = 'hidden';
		}
	}

	function closeMobileMenu() {
		mobileMenuOpen = false;
		activeDropdown = null;
		if (typeof document !== 'undefined') {
			document.body.style.overflow = '';
		}
	}

	function closeAll() {
		activeDropdown = null;
		closeMobileMenu();
	}

	onMount(() => {
		const handleEscape = (e: KeyboardEvent) => {
			if (e.key === 'Escape') closeAll();
		};

		window.addEventListener('keydown', handleEscape);

		return () => {
			window.removeEventListener('keydown', handleEscape);
			if (typeof document !== 'undefined') {
				document.body.style.overflow = '';
			}
		};
	});
</script>

<header class="sticky top-0 z-50 border-b border-black/5 bg-white/90 backdrop-blur-xl">
	<div class="mx-auto flex max-w-7xl items-center justify-between px-4 py-4 sm:px-6 lg:px-8">
		<div class="flex items-center gap-3">
			<div
				class="flex h-11 w-11 items-center justify-center rounded-2xl bg-[#10324a] text-white shadow-sm"
			>
				<MessageSquareHeart size={20} />
			</div>
			<div>
				<div class="text-[15px] font-semibold tracking-tight">Clarinth AI</div>
				<div class="text-xs text-slate-500">AI companion for clarity & growth</div>
			</div>
		</div>

		<nav class="relative hidden items-center gap-8 lg:flex">
			{#each navItems as item}
				<div class="relative">
					<button
						type="button"
						class="flex items-center gap-1 text-sm text-slate-700 transition hover:text-[#10324a]"
						on:click={() => toggleDropdown(item.label)}
						aria-expanded={activeDropdown === item.label}
						aria-haspopup="true"
					>
						{item.label}
						<ChevronDown size={16} />
					</button>

					{#if activeDropdown === item.label}
						<div
							class="absolute top-full left-0 mt-3 w-56 rounded-2xl border border-slate-100 bg-white p-2 shadow-xl"
						>
							{#each item.children ?? [] as child}
								<a
									href={child.href}
									class="block rounded-xl px-3 py-2 text-sm text-slate-600 transition hover:bg-slate-50 hover:text-[#10324a]"
								>
									{child.label}
								</a>
							{/each}
						</div>
					{/if}
				</div>
			{/each}
		</nav>

		<div class="hidden items-center gap-3 lg:flex">
			<a
				href="#contact"
				class="rounded-full border border-slate-300 px-4 py-2 text-sm font-medium text-slate-700 transition hover:border-[#10324a] hover:text-[#10324a]"
			>
				Contact
			</a>
			<a
				href="#start"
				class="inline-flex items-center gap-2 rounded-full bg-[#10324a] px-5 py-2.5 text-sm font-semibold text-white shadow-sm transition hover:bg-[#0b2535]"
			>
				Start your journey <ArrowRight size={16} />
			</a>
		</div>

		<button
			type="button"
			class="inline-flex h-11 w-11 items-center justify-center rounded-2xl border border-slate-300 bg-white text-slate-700 lg:hidden"
			aria-label="Open menu"
			aria-expanded={mobileMenuOpen}
			on:click={openMobileMenu}
		>
			<Menu size={20} />
		</button>
	</div>

	{#if mobileMenuOpen}
		<div
			class="fixed inset-0 z-50 bg-black/40 lg:hidden"
			aria-hidden="true"
			on:click={closeMobileMenu}
		></div>

		<aside
			class="fixed top-0 right-0 z-[60] w-[92vw] max-w-md overflow-hidden bg-white shadow-2xl lg:hidden"
			style="height: 100dvh;"
			aria-label="Mobile navigation"
			on:click|stopPropagation
		>
			<div class="flex h-full flex-col">
				<div
					class="flex flex-none items-center justify-between border-b border-slate-200 px-5 py-4"
				>
					<div class="flex items-center gap-3">
						<div
							class="flex h-10 w-10 items-center justify-center rounded-2xl bg-[#10324a] text-white"
						>
							<MessageSquareHeart size={18} />
						</div>
						<div class="font-semibold">Clarinth AI</div>
					</div>

					<button
						type="button"
						class="inline-flex h-10 w-10 items-center justify-center rounded-xl border border-slate-200"
						aria-label="Close menu"
						on:click={closeMobileMenu}
					>
						<X size={18} />
					</button>
				</div>

				<div class="flex-1 overflow-y-auto px-5 py-6">
					<div class="space-y-4">
						{#each navItems as item}
							<section class="rounded-2xl border border-slate-100 bg-white">
								<button
									type="button"
									class="flex w-full items-center justify-between px-4 py-3 text-left text-sm font-medium text-slate-800"
									on:click={() => toggleDropdown(item.label)}
									aria-expanded={activeDropdown === item.label}
								>
									<span>{item.label}</span>
									<ChevronDown
										size={16}
										class={`transition-transform ${activeDropdown === item.label ? 'rotate-180' : ''}`}
									/>
								</button>

								{#if activeDropdown === item.label}
									<div class="px-3 pb-3">
										<div class="grid gap-2">
											{#each item.children ?? [] as child}
												<a
													href={child.href}
													class="flex items-center justify-between rounded-2xl bg-slate-50 px-4 py-3 text-sm font-medium text-slate-700 transition hover:bg-slate-100 hover:text-[#10324a]"
													on:click={closeMobileMenu}
												>
													<span>{child.label}</span>
													<ChevronRight size={16} class="text-slate-400" />
												</a>
											{/each}
										</div>
									</div>
								{/if}
							</section>
						{/each}
					</div>

					<a
						href="#start"
						class="mt-6 flex items-center justify-center gap-2 rounded-full bg-[#10324a] px-5 py-3 font-semibold text-white transition hover:bg-[#0b2535]"
						on:click={closeMobileMenu}
					>
						Start your journey <ArrowRight size={16} />
					</a>
				</div>
			</div>
		</aside>
	{/if}
</header>
