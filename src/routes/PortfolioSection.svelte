<script lang="ts">
	import SectionHeader from '$lib/components/SectionHeader.svelte';
	import ProjectBlock from '$lib/components/ProjectBlock.svelte';

	type Project = {
		name: string;
		description: string;
		imageSrc: string;
		textFirst: boolean;
	};
	const myProjects: Project[] = [
		{
			name: 'Kasado',
			description:
				'Some text about Kasado. Some text about Kasado.' +
				'Some text about Kasado. Some text about Kasado. ' +
				'Some text about Kasado. Kasado. Some text about Kasado.' +
				'Some text about Kasado.',
			imageSrc:
				'https://cdn.dribbble.com/users/4001713/screenshots/14872385/media/7dd9babdcdfe199b97a060991f4c1a08.png?compress=1&resize=400x300&vertical=top',
			textFirst: true
		},
		{
			name: 'Kapiot',
			description:
				'Lorem Ipsum is simply dummy text of the printing and' +
				"typesetting industry. Lorem Ipsum has been the industry's " +
				'standard dummy text ever since the 1500s, when an unknown ' +
				'printer took a galley of type and scrambled it to make ',
			imageSrc:
				'https://cdn.dribbble.com/users/4001713/screenshots/14872385/media/7dd9babdcdfe199b97a060991f4c1a08.png?compress=1&resize=400x300&vertical=top',
			textFirst: false
		},
		{
			name: 'Marnikko',
			description:
				'Some text about Marnikko. Some text about Marnikko.' +
				'Some text about Marnikko. Some text about Marnikko. ' +
				'Some text about Marnikko. Some text about Marnikko.' +
				'Some text about Marnikko.',
			imageSrc:
				'https://cdn.dribbble.com/users/4001713/screenshots/14872385/media/7dd9babdcdfe199b97a060991f4c1a08.png?compress=1&resize=400x300&vertical=top',
			textFirst: true
		}
	];
</script>

<section id="portfolio-section" class="min-h-screen">
	<SectionHeader sectionTitle={'Some of my Work'} />

	<div class="flex flex-col items-center justify-center">
		{#each myProjects as project}
			<ProjectBlock {...project} />
		{/each}
	</div>
</section>
