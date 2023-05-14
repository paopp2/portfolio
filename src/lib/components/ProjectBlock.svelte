<script lang="ts">
	import kasadoSS from '$lib/assets/project_screenshots/kasado.png';
	import kapiotSS from '$lib/assets/project_screenshots/kapiot.png';
	import marnikkoSS from '$lib/assets/project_screenshots/marnikko.png';

	export let name: string;
	export let description: string;
	export let textFirst: boolean = true;

	const projectSSMap: { [projectName: string]: string } = {
		Kasado: kasadoSS,
		Kapiot: kapiotSS,
		Marnikko: marnikkoSS
	};
</script>

<div
	class="flex rounded-[35px] bg-[#111f3b] shadow-2xl justify-center mb-20 hover:scale-[1.03] transition">
	{#if textFirst}
		<div class="text-half">
			<h1>{name}</h1>
			<p>{description}</p>
		</div>

		<img class="img-half" src={projectSSMap[name]} alt="random_alt" />
	{:else}
		<img class="img-half" src={projectSSMap[name]} alt="random_alt" />

		<div class="text-half">
			<h1>{name}</h1>
			<p>{description}</p>
		</div>
	{/if}
</div>

<style>
	.text-half {
		@apply w-1/2 p-16;
	}

	.text-half > h1 {
		@apply mb-2 text-5xl font-bold leading-tight text-[var(--text-color)] pb-8;
	}

	.text-half > p {
		@apply mb-4 text-[#7d8092];
	}

	.img-half {
		@apply rounded-[35px] object-cover w-1/2 p-3;
	}
</style>
