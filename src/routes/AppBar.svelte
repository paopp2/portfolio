<script lang="ts">
	import logo from '$lib/assets/logo.png';
	import Headroom from 'headroom.js';
	import { browser } from '$app/environment';
	import { onMount } from 'svelte';
	import mixpanel from 'mixpanel-browser';
	import resumeLink from '$lib/assets/resume.pdf';

	const idToSecNameMap: { [target: string]: string } = {
		'hero-section': 'Home',
		'about-section': 'About',
		'portfolio-section': 'Portfolio',
		'contact-section': 'Contact'
	};
	const sectionIds: string[] = Object.keys(idToSecNameMap);
	let currentSecId: string = sectionIds[0];
	let stagedSecId: string = sectionIds[0];

	onMount(async () => {
		mixpanel.init('7ccb08fcc07a7d7c1aa6d5d86e7acab6');
		mixpanel.track('Opened website');

		if (browser) {
			const header = document.querySelector('#nav-bar');
			const headroom = new Headroom(header!);
			headroom.init();
		}

		const observer = new IntersectionObserver((entries) => {
			entries.forEach((entry) => {
				if (entry.isIntersecting) {
					// Stage the intersecting section
					stagedSecId = entry.target.id;
				} else {
					// Wait to completely leave previous section
					// before setting the staged section as current
					if (entry.target.id !== stagedSecId) {
						currentSecId = stagedSecId;
						mixpanel.track('Navigated site', {
							section: idToSecNameMap[currentSecId]
						});
					}
				}
			});
		});

		const elements = document.querySelectorAll('section');
		elements.forEach((el) => observer.observe(el));
	});

	$: getNavBarLinkClass = (secId: string) => {
		return currentSecId === secId
			? 'block py-2 pl-3 pr-4 text-white bg-blue-500 rounded md:bg-transparent md:text-blue-500 md:p-0 dark:text-white text-lg'
			: 'block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent text-lg';
	};

	function openedResume() {
		mixpanel.track('Opened resume');
	}
</script>

<nav id="nav-bar" class="headroom bg-[#0b1426]/90 backdrop-blur-md">
	<div
		class="h-24 container mx-auto flex flex-wrap items-center justify-between">
		<a href="/" class="flex items-center">
			<img src={logo} class="mr-3 h-6 sm:h-12" alt="My logo" />
			<span
				class="self-center whitespace-nowrap text-2xl font-semibold dark:text-white"
				>Paolo Pepito</span>
		</a>
		<button
			data-collapse-toggle="navbar-default"
			type="button"
			class="ml-3 inline-flex items-center rounded-lg p-2 text-sm text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600 md:hidden"
			aria-controls="navbar-default"
			aria-expanded="false">
			<span class="sr-only">Open main menu</span>
			<svg
				class="h-6 w-6"
				aria-hidden="true"
				fill="currentColor"
				viewBox="0 0 20 20"
				xmlns="http://www.w3.org/2000/svg"
				><path
					fill-rule="evenodd"
					d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
					clip-rule="evenodd" /></svg>
		</button>
		<div class="hidden w-full md:block md:w-auto" id="navbar-default">
			<ul class="flex flex-row space-x-8 items-center">
				{#each sectionIds as secId}
					<li>
						<a
							href={'#' + secId}
							class={getNavBarLinkClass(secId)}
							aria-current="page">{idToSecNameMap[secId]}</a>
					</li>
				{/each}
				<a href={resumeLink} target="_blank" rel="noreferrer">
					<button
						on:click={openedResume}
						type="button"
						class="text-blue-500 hover:text-white hover:font-bold border border-blue-500 hover:bg-blue-500 rounded-lg text-lg px-5 py-2 text-center"
						>Resume</button>
				</a>
			</ul>
		</div>
	</div>
</nav>

<style>
	.headroom {
		will-change: transform;
		transition: transform 200ms linear;
	}
	.headroom--pinned {
		transform: translateY(0%);
	}
	.headroom--unpinned {
		transform: translateY(-100%);
	}
	.headroom--not-top {
		@apply shadow-2xl;
	}
</style>
