<script>
	import AppBar from "./AppBar.svelte";
	import HeroSection from "./HeroSection.svelte";
</script>

<div>
  <AppBar/>
  <main class="absolute top-0 -z-10">
    <HeroSection/>
    <HeroSection/>
    <HeroSection/>
  </main>
</div>

<style lang="postcss">
  :global(html) {
    background-color: #0b1426;
  }
</style>