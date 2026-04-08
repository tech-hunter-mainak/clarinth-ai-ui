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

<div class="min-h-screen bg-white flex items-center justify-center px-4">
	<div class="w-full max-w-2xl text-center">

		<!-- Error Code -->
		<div class="text-6xl font-bold tracking-tight text-[#10324a] mb-4">
			{status}
		</div>

		<!-- Heading -->
		<h1 class="text-2xl sm:text-3xl font-semibold text-slate-900 mb-3">
			Something interrupted your flow
		</h1>

		<!-- Description -->
		<p class="text-slate-600 leading-7 max-w-md mx-auto mb-8">
			{error?.message ??
			"We couldn’t find what you were looking for. Let’s help you get back to clarity."}
		</p>

		<!-- Actions -->
		<div class="flex flex-col sm:flex-row items-center justify-center gap-3 mb-10">
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
			<p class="text-sm text-slate-500 mb-4">
				Or continue your journey
			</p>

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