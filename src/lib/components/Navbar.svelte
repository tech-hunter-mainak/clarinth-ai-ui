<script>
	import Button from './Button.svelte';

	let mobileMenuOpen = false;
</script>

<!-- Navigation -->
<header class="fixed top-0 z-[1000] w-full border-b border-gray-100 bg-white/80 backdrop-blur-xl">
	<div class="mx-auto flex max-w-7xl items-center justify-between px-6 py-5">
		<!-- Left Section: Logo + Tagline -->
		<div class="flex items-center space-x-3">
			<img src="/logo.svg" alt="Tests for Travel Logo" class="h-10" />
			<span class="text-xs tracking-wide text-gray-600">Powered by Innovest</span>
		</div>

		<!-- Desktop Navigation -->
		<nav class="hidden items-center space-x-10 text-sm font-medium lg:flex">
			<a href="#" class="text-gray-700 transition hover:text-black">About</a>
			<a href="#" class="text-gray-700 transition hover:text-black">Contact</a>
			<a href="#" class="text-gray-700 transition hover:text-black">Register</a>
		</nav>

		<!-- Right Side (24/7 Info) -->
		<div class="hidden flex-col text-right text-sm lg:flex">
			<Button text="Try Now" link="https://clarinth.ai"></Button>
		</div>

		<!-- Mobile Menu Button -->
		<button
			class="rounded-md border border-gray-300 p-2 text-gray-700 transition hover:bg-gray-100 lg:hidden"
			on:click={() => (mobileMenuOpen = !mobileMenuOpen)}
		>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-6 w-6"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
			>
				{#if !mobileMenuOpen}
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M4 6h16M4 12h16M4 18h16"
					/>
				{:else}
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M6 18L18 6M6 6l12 12"
					/>
				{/if}
			</svg>
		</button>
	</div>

	<!-- Mobile Menu Dropdown -->
	{#if mobileMenuOpen}
		<div class="space-y-4 border-t border-gray-200 bg-white px-6 py-4 text-sm shadow-md lg:hidden">
			<a href="#" class="block text-gray-700 transition hover:text-black">About</a>
			<a href="#" class="block text-gray-700 transition hover:text-black">Contact</a>
			<a href="#" class="block text-gray-700 transition hover:text-black">Register</a>

			<button
				class="w-full rounded-md bg-black px-6 py-2 font-medium text-white shadow transition hover:opacity-90"
			>
				Buy
			</button>
		</div>
	{/if}
</header>
