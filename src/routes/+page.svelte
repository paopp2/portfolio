<script>
	import HeroSection from './HeroSection.svelte';
	import PortfolioSection from './PortfolioSection.svelte';
	import AboutSection from './AboutSection.svelte';
	import ContactSection from './ContactSection.svelte';
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="true" />
<link
	href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;400;700&display=swap"
	rel="stylesheet" />
<div>
	<HeroSection />
	<AboutSection />
	<div class="pt-32" />
	<PortfolioSection />
	<div class="pt-32" />
	<ContactSection />
</div>

<style lang="postcss">
	:global(html) {
		scroll-behavior: smooth;
		font-family: 'Roboto', sans-serif;
		background-color: #0b1426;

		/* Shared style variables */
		--text-color: #ced6f5;
	}
</style>
