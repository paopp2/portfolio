<script lang="ts">
	export let name: string;
	export let description: string;
	export let imageSrc: string;
	export let textFirst: boolean = true;
</script>

<div class="flex rounded-[35px] bg-[#111f3b] shadow-2xl justify-center mb-20">
	{#if textFirst}
		<div class="text-half">
			<h1>{name}</h1>
			<p>{description}</p>
		</div>

		<img class="img-half" src={imageSrc} alt="random_alt" />
	{:else}
		<img class="img-half" src={imageSrc} alt="random_alt" />

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
