<script lang="ts">
	import SectionHeader from '$lib/components/SectionHeader.svelte';
	import ProjectBlock from '$lib/components/ProjectBlock.svelte';
	import siteContent from '$lib/assets/site-content.json';

	const myProjects = siteContent.portfolio.projects.map((projObj, i) => ({
		...projObj,
		textFirst: i % 2 === 1 // Alternate text first layout
	}));
</script>

<section id="portfolio-section" class="min-h-screen">
	<SectionHeader sectionTitle={'Some of my Work'} />

	<div class="flex flex-col items-center justify-center">
		{#each myProjects as project}
			<ProjectBlock {...project} />
		{/each}
	</div>
</section>
