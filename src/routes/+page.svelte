<script>
	import HeroSection from './HeroSection.svelte';
	import PortfolioSection from './PortfolioSection.svelte';
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="true" />
<link
	href="https://fonts.googleapis.com/css2?family=Roboto:wght@100;400;700&display=swap"
	rel="stylesheet" />
<div>
	<HeroSection />
	<PortfolioSection />
</div>

<style lang="postcss">
	:global(html) {
		scroll-behavior: smooth;
		font-family: 'Roboto', sans-serif;
	}
</style>
