<script lang="ts">
	import { onMount } from 'svelte';
	import { tweened } from 'svelte/motion';
	import { cubicOut } from 'svelte/easing';
	import lottie from 'lottie-web';
	import arrowDownLottieData from '$lib/assets/arrow-down-lottie.json';
	import siteContent from '$lib/assets/site-content.json';

	const { name, middleText, bottomText, primaryButtonTxt } = siteContent.hero;

	let arrowDownLottieContainer: HTMLElement;
	onMount(async () => {
		lottie.loadAnimation({
			container: arrowDownLottieContainer,
			animationData: arrowDownLottieData
		});

		[padding0, padding1, padding2, padding3].forEach((p) => p.set(20));
		[alpha0, alpha1, alpha2, alpha3].forEach((a) => a.set(1.0));
	});

	const padding0 = tweened(0, getAnimationConfig());
	const alpha0 = tweened(0.0, getAnimationConfig());

	const padding1 = tweened(0, getAnimationConfig(1));
	const alpha1 = tweened(0, getAnimationConfig(1));

	const padding2 = tweened(0, getAnimationConfig(2));
	const alpha2 = tweened(0, getAnimationConfig(2));

	const padding3 = tweened(0, getAnimationConfig(3, 1500));
	const alpha3 = tweened(0, getAnimationConfig(3));

	function getAnimationConfig(order = 0, duration: number = 1000) {
		const staggerDelayMs = 90;
		return {
			duration: duration,
			easing: cubicOut,
			delay: staggerDelayMs * order
		};
	}
</script>

<section id="hero-section">
	<div
		class="container mx-auto flex flex-col h-screen justify-center pl-[180px] pr-[200px] font-bold text-white">
		<div style="padding-left: {$padding0}px; opacity: {$alpha0}">
			<h1 class="text-[110px] text-[#ced6f5]">{name}</h1>
		</div>
		<div style="padding-left: {$padding1}px; opacity: {$alpha1}">
			<h2 class="pb-8 text-[50px] font-normal text-[#8a92af]">
				{middleText}
			</h2>
		</div>
		<div style="padding-left: {$padding2}px; opacity: {$alpha2}">
			<p class="pb-14 text-[18.5px] font-normal text-[#737c97] whitespace-pre">
				{bottomText}
			</p>
		</div>
		<div style="padding-left: {$padding3}px; opacity: {$alpha3}">
			<a href="#about-section">
				<button
					type="button"
					class="mr-2 mb-2 h-[4.5rem] rounded-2xl bg-gradient-to-r from-blue-500 via-blue-600 to-blue-700 px-4 py-3 text-center hover:bg-gradient-to-br focus:outline-none flex items-center justify-center">
					<span class="pl-4 text-xl font-extrabold text-white "
						>{primaryButtonTxt}</span>
					<div bind:this={arrowDownLottieContainer} class="h-14 w-14" />
				</button>
			</a>
		</div>
	</div>
</section>
