<script>
	import HeroSection from './HeroSection.svelte';
	import PortfolioSection from './PortfolioSection.svelte';
	import AboutSection from './AboutSection.svelte';
	import ContactSection from './ContactSection.svelte';
	import AppBar from './AppBar.svelte';
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="true" />
<link
	href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;400;700&display=swap"
	rel="stylesheet" />

<header class="fixed top-0 left-0 right-0 z-50">
	<AppBar />
</header>
<main>
	<HeroSection />
	<div class="pt-8" />
	<AboutSection />
	<div class="pt-32" />
	<PortfolioSection />
	<div class="pt-8" />
	<ContactSection />
</main>

<style lang="postcss">
	:global(html) {
		scroll-behavior: smooth;
		font-family: 'Roboto', sans-serif;
		background-color: #0b1426;
		color: #7d8092;

		/* Shared style variables */
		--text-color: #ced6f5;
		--accent: #7de1c5;
	}
</style>
