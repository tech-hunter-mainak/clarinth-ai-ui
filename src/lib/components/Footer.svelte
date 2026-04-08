<script lang="ts">
	import Button from './Button.svelte';
	import { MessageSquareHeart } from 'lucide-svelte';

	type NavGroup = {
		title: string;
		items: { label: string; href: string }[];
	};

	const navGroups: NavGroup[] = [
		{
			title: 'Product',
			items: [
				{ label: 'AI Companion', href: '#' },
				{ label: 'Conversations', href: '#' },
				{ label: 'Emotional Support', href: '#' },
				{ label: 'Self-Growth Tools', href: '#' }
			]
		},
		{
			title: 'About Clarinth',
			items: [
				{ label: 'About Us', href: '#' },
				{ label: 'Vision & Mission', href: '#' },
				{ label: 'Careers', href: '#' },
				{ label: 'Contact', href: '#' },
				{ label: 'Help / FAQs', href: '#' }
			]
		},
		{
			title: 'Use Cases',
			items: [
				{ label: 'Students', href: '#' },
				{ label: 'Professionals', href: '#' },
				{ label: 'Personal Growth', href: '#' }
			]
		},
		{
			title: 'For Partners',
			items: [
				{ label: 'Integrations', href: '#' },
				{ label: 'API Access', href: '#' },
				{ label: 'Workshops & Programs', href: '#' },
				{ label: 'Institutional Use', href: '#' }
			]
		}
	];
</script>

<footer class="border-t border-black/5 bg-white">
	<div class="mx-auto max-w-7xl px-4 py-10 sm:px-6 lg:px-8">
		<div class="grid gap-10 lg:grid-cols-12">
			<div class="lg:col-span-4">
				<div class="flex items-center gap-3">
					<div
						class="flex h-11 w-11 items-center justify-center rounded-2xl bg-[#10324a] text-white"
					>
						<MessageSquareHeart size={20} />
					</div>
					<div>
						<div class="font-semibold">Clarinth AI</div>
						<div class="text-sm text-slate-500">© 2026</div>
					</div>
				</div>
				<p class="mt-4 max-w-md text-sm leading-7 text-slate-600">
					Clarinth AI is your intelligent companion for meaningful conversations, emotional clarity,
					and continuous self-growth—available anytime you need it.
				</p>
			</div>

			<div class="lg:col-span-8">
				<div class="grid gap-8 sm:grid-cols-2 xl:grid-cols-4">
					{#each navGroups as group (group.items)}
						<div>
							<h3 class="text-sm font-semibold text-slate-900">{group.title}</h3>
							<ul class="mt-4 space-y-3">
								{#each group.items as item (item.label)}
									<li>
										<a
											href={item.href}
											class="text-sm text-slate-600 transition hover:text-[#10324a]">{item.label}</a
										>
									</li>
								{/each}
							</ul>
						</div>
					{/each}
				</div>
			</div>
		</div>

		<div
			class="mt-10 flex flex-col gap-4 border-t border-slate-200 pt-6 text-sm text-slate-500 sm:flex-row sm:items-center sm:justify-between"
		>
			<div class="flex flex-wrap gap-x-4 gap-y-2">
				<a href="#" class="transition hover:text-[#10324a]">Privacy Policy</a>
				<a href="#" class="transition hover:text-[#10324a]">Terms &amp; Conditions</a>
				<a href="#" class="transition hover:text-[#10324a]">Sitemap</a>
				<a href="#" class="transition hover:text-[#10324a]">Trust & Safety</a>
			</div>
			<div class="max-w-2xl text-sm leading-7 text-slate-500">
				Clarinth AI is not a substitute for professional medical or psychological advice. If you are
				experiencing a crisis or emergency, please contact local emergency services or a qualified
				professional immediately.
			</div>
		</div>
	</div>
</footer>
