<script lang="ts">
	import { page } from '$app/stores';
	import { goto } from '$app/navigation';
	import { MessageSquareHeart, ArrowRight, Home, RefreshCw } from 'lucide-svelte';

	$: status = $page.status;
	$: error = $page.error;

	function goHome() {
		goto('/');
	}

	function retry() {
		location.reload();
	}
</script>

<svelte:head>
	<title>{status} • Clarinth AI</title>
</svelte:head>

<div class="flex min-h-screen items-center justify-center bg-white px-4">
	<div class="w-full max-w-2xl text-center">
		<!-- Error Code -->
		<div class="mb-4 text-6xl font-bold tracking-tight text-[#10324a]">
			{status}
		</div>

		<!-- Heading -->
		<h1 class="mb-3 text-2xl font-semibold text-slate-900 sm:text-3xl">
			Something interrupted your flow
		</h1>

		<!-- Description -->
		<p class="mx-auto mb-8 max-w-md leading-7 text-slate-600">
			{error?.message ??
				'We couldn’t find what you were looking for. Let’s help you get back to clarity.'}
		</p>

		<!-- Actions -->
		<div class="mb-10 flex flex-col items-center justify-center gap-3 sm:flex-row">
			<button
				on:click={goHome}
				class="inline-flex items-center justify-center gap-2 rounded-full bg-[#10324a] px-6 py-3 text-sm font-semibold text-white shadow-sm transition hover:bg-[#0b2535]"
			>
				<Home size={16} />
				Go to homepage
			</button>

			<button
				on:click={retry}
				class="inline-flex items-center justify-center gap-2 rounded-full border border-slate-300 px-6 py-3 text-sm font-medium text-slate-700 transition hover:border-[#10324a] hover:text-[#10324a]"
			>
				<RefreshCw size={16} />
				Try again
			</button>
		</div>

		<!-- Divider -->
		<div class="border-t border-slate-200 pt-8">
			<p class="mb-4 text-sm text-slate-500">Or continue your journey</p>

			<!-- Quick Links -->
			<div class="flex flex-wrap justify-center gap-3">
				<a
					href="#"
					class="rounded-full bg-slate-50 px-4 py-2 text-sm font-medium text-slate-700 transition hover:bg-slate-100 hover:text-[#10324a]"
				>
					Start a conversation
				</a>

				<a
					href="#"
					class="rounded-full bg-slate-50 px-4 py-2 text-sm font-medium text-slate-700 transition hover:bg-slate-100 hover:text-[#10324a]"
				>
					Explore features
				</a>

				<a
					href="#"
					class="rounded-full bg-slate-50 px-4 py-2 text-sm font-medium text-slate-700 transition hover:bg-slate-100 hover:text-[#10324a]"
				>
					Read resources
				</a>
			</div>
		</div>
	</div>
</div>
