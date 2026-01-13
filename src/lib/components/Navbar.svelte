<script>
	import Button from "./Button.svelte";

	let mobileMenuOpen = false;
</script>

<!-- Navigation -->
<header class="sticky top-0 z-[1000] w-full bg-white/80 backdrop-blur-xl border-b border-gray-100">
	<div class="mx-auto flex max-w-7xl items-center justify-between px-6 py-5">

		<!-- Left Section: Logo + Tagline -->
		<div class="flex items-center space-x-3">
			<img src="/logo.svg" alt="Tests for Travel Logo" class="h-10" />
			<span class="text-xs text-gray-600 tracking-wide">Powered by Innovest</span>
		</div>

		<!-- Desktop Navigation -->
		<nav class="hidden lg:flex items-center space-x-10 text-sm font-medium">
			<a href="#" class="text-gray-700 hover:text-black transition">About</a>
			<a href="#" class="text-gray-700 hover:text-black transition">Contact</a>
			<a href="#" class="text-gray-700 hover:text-black transition">Register</a>
		</nav>

		<!-- Right Side (24/7 Info) -->
		<div class="hidden lg:flex flex-col text-right text-sm">
			<Button text="Try Now" link="https://clarinth.ai"></Button>
		</div>

		<!-- Mobile Menu Button -->
		<button
			class="lg:hidden rounded-md border border-gray-300 p-2 text-gray-700 hover:bg-gray-100 transition"
			on:click={() => (mobileMenuOpen = !mobileMenuOpen)}>
			<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none"
				viewBox="0 0 24 24" stroke="currentColor">
				{#if !mobileMenuOpen}
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
						d="M4 6h16M4 12h16M4 18h16" />
				{:else}
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
						d="M6 18L18 6M6 6l12 12" />
				{/if}
			</svg>
		</button>
	</div>

	<!-- Mobile Menu Dropdown -->
	{#if mobileMenuOpen}
		<div class="lg:hidden border-t border-gray-200 bg-white px-6 py-4 space-y-4 text-sm shadow-md">
			<a href="#" class="block text-gray-700 hover:text-black transition">About</a>
			<a href="#" class="block text-gray-700 hover:text-black transition">Contact</a>
			<a href="#" class="block text-gray-700 hover:text-black transition">Register</a>

			<button class="w-full rounded-md bg-black px-6 py-2 text-white font-medium shadow hover:opacity-90 transition">
				Buy
			</button>
		</div>
	{/if}
</header>
