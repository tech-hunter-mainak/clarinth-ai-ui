<script lang="ts">
	import Button from '$lib/components/Button.svelte';
	import { slide } from 'svelte/transition';

	interface FAQ {
		question: string;
		answer: string;
		open: boolean;
	}

	let faqs: FAQ[] = [
		{
			question: 'What is Clarinth AI?',
			answer:
				'Clarinth AI is an intelligent conversational companion focused on mental wellness and reflective self-growth. It supports meaningful, empathetic conversations designed to help users gain clarity and insight.',
			open: false
		},
		{
			question: 'Is Clarinth AI a replacement for therapy?',
			answer:
				'No. Clarinth AI is designed to assist with guidance and emotional support, but it is not a licensed therapist. It should not be used as a substitute for professional medical care or crisis intervention.',
			open: false
		},
		{
			question: 'Is my data secure?',
			answer:
				'Yes. Clarinth AI uses secure cloud systems and industry-standard encryption to protect user information. Your conversations are confidential and are not shared without your explicit consent.',
			open: false
		},
		{
			question: 'Can I use Clarinth AI anytime?',
			answer:
				'Yes. The service is available 24/7, offering continuous access whenever you need insights, support, or meaningful conversation.',
			open: false
		},
		{
			question: 'Does Clarinth AI adapt to my behavior?',
			answer:
				'Yes. Over time, Clarinth AI observes communication patterns and preferences to personalize responses and deliver more relevant guidance.',
			open: false
		}
	];

	function toggleFAQ(index: number) {
		faqs = faqs.map((faq, i) => ({
			...faq,
			open: i === index ? !faq.open : faq.open
		}));
	}
</script>

<div class="flex min-h-screen w-full flex-col bg-[#f3f7f5]">
	<div class="mx-auto flex w-full flex-col py-20">
		<!-- Page Title -->
		<div class="mb-14 text-center">
			<h1 class="text-4xl font-bold text-gray-900">Frequently Asked Questions</h1>
			<p class="mx-auto mt-3 max-w-xl text-gray-600">
				Discover everything you need to know before getting started with Clarinth AI.
			</p>
		</div>

		<!-- FAQs -->
		<div class="mx-40 space-y-4">
			{#each faqs as faq, i}
				<div
					class="hover:-gray-300 overflow-hidden rounded-xl bg-white shadow-sm transition hover:shadow-lg"
				>
					<!-- Header -->
					<button
						class="flex w-full items-center justify-between px-6 py-5 text-left"
						on:click={() => toggleFAQ(i)}
					>
						<h3 class="text-lg font-semibold text-gray-900">{faq.question}</h3>

						<!-- Rotating + icon -->
						<span class="rotate text-3xl leading-none text-gray-700 {faq.open ? 'open' : ''}">
							+
						</span>
					</button>

					<!-- Body -->
					{#if faq.open}
						<div class="bg-gray-50 px-6 pb-5 text-gray-700" transition:slide|local|fade>
							<p class="text-sm leading-relaxed">
								{faq.answer}
							</p>
						</div>
					{/if}
				</div>
			{/each}
		</div>

		<!-- CTA -->
		<section
			class="relative mt-20 flex w-full flex-col items-start justify-between overflow-hidden rounded-xl bg-gradient-to-br from-[#F4F7FB] to-white px-20 py-16 md:flex-row md:items-center"
		>
			<!-- Background Lines -->
			<div class="pointer-events-none absolute inset-0 opacity-15">
				<svg
					viewBox="0 0 600 400"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
					class="h-full w-full"
				>
					<path d="M100 200c80-80 200-80 280 0s200 80 280 0" stroke="#dbe1ea" stroke-width="2" />
					<path d="M50 250c100-100 300-100 400 0s300 100 400 0" stroke="#e3e8ef" stroke-width="2" />
				</svg>
			</div>

			<div class="relative z-10 max-w-xl">
				<p class="mb-3 text-xs tracking-widest text-[#4A5A78]">NEED MORE HELP?</p>
				<h1 class="text-3xl leading-tight font-semibold text-[#0B163F] md:text-4xl">
					Still Have Questions?<br />We’re Here to Support You.
				</h1>
			</div>

			<div class="relative z-10 mt-8 md:mt-0">
				<Button text="Contact Support" />
			</div>
		</section>
	</div>
</div>

<style>
	.rotate {
		transition: transform 0.3s ease;
	}
	.rotate.open {
		transform: rotate(45deg);
	}
</style>
