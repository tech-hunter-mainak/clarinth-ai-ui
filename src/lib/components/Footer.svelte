<script>
	import Button from './Button.svelte';
	import icon_mail from '$lib/assets/mail.svg';
	import icon_plus from '$lib/assets/plus.svg';
</script>

<footer
	class="bg-primary relative mt-10 mb-2 w-full pt-10 pb-6 text-(--heading-color) md:left-5! md:w-[calc(100%-40px)] md:rounded-[50px]"
>
	<div class="mx-auto grid max-w-7xl grid-cols-1 gap-10 px-6 md:grid-cols-3">
		<!-- Left block -->
		<div class="space-y-4">
			<p class="leading-tight font-semibold">
				Clarinth AI<br />
				Mental Wellness Companion
			</p>
			<p class="text-sm leading-relaxed">
				Intelligent and compassionate conversations<br />
				designed to support clarity and emotional wellbeing.
			</p>

			<Button text="aiclarinth@gmail.com" link="mailto:aiclarinth@gmail.com" icon={icon_mail}
			></Button>
		</div>

		<!-- Middle block -->
		<div class="space-y-4">
			<p class="font-semibold">Explore</p>
			<p class="text-sm leading-relaxed">
				Features<br />
				About Clarinth<br />
				Contact & Support<br />
				Start Your Journey
			</p>

			<Button text="Ask a Question" link="/faqs" icon={icon_plus}></Button>
		</div>

		<!-- Right block (social networks) -->
		<div class="flex justify-center md:justify-end">
			<div class="flex flex-col items-center rounded-xl bg-white px-8 py-6 text-center shadow">
				<p class="mb-4 font-semibold">Connect with Us</p>

				<!-- Social icons row -->
				<div class="mb-4 flex space-x-4">
					<a href="#" class="flex h-8 w-8 items-center justify-center rounded-full bg-[#0c2b2e]">
						<i class="fab fa-facebook-f text-white"></i>
					</a>
					<a href="#" class="flex h-8 w-8 items-center justify-center rounded-full bg-[#0c2b2e]">
						<i class="fab fa-linkedin-in text-white"></i>
					</a>
					<a href="#" class="flex h-8 w-8 items-center justify-center rounded-full bg-[#0c2b2e]">
						<i class="fab fa-youtube text-white"></i>
					</a>
				</div>

				<img src="/images/bird.png" alt="Clarinth Bird Icon" class="w-12" />
			</div>
		</div>
	</div>

	<!-- Footer bottom links -->
	<div class="mx-auto mt-10 max-w-7xl px-6">
		<div class="flex flex-wrap justify-center gap-4 text-sm">
			<a href="https://clarinth.ai/">Home</a>
			<span>|</span>
			<a href="https://clarinth.ai/">Features</a>
			<span>|</span>
			<a href="https://clarinth.ai/">About</a>
			<span>|</span>
			<a href="https://clarinth.ai/">Contact</a>
			<span>|</span>
			<a href="#">Privacy Policy</a>
			<span>|</span>
			<a href="#">Terms of Service</a>
		</div>
	</div>
</footer>

<div class="mb-4 flex w-full flex-col justify-between px-5 md:flex-row">
	<div>&copy; {new Date().getFullYear()} | All Rights Reserved.</div>
	<div>Made in India</div>
</div>
