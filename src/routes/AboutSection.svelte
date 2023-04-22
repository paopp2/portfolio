<script>
	import SectionHeader from '$lib/components/SectionHeader.svelte';
	import siteContent from '$lib/assets/site-content.json';
	import webIcon from '$lib/assets/icons/web.svg';
	import mobileIcon from '$lib/assets/icons/mobile.svg';
	import serverIcon from '$lib/assets/icons/server.svg';
	import terminalIcon from '$lib/assets/icons/terminal.svg';

	const greeting = siteContent.about.greeting;
	const description = siteContent.about.description;

	const webSkills = siteContent.about.skills.web;
	const mobileSkills = siteContent.about.skills.mobile;
	const toolsAndLangs = siteContent.about.skills.toolsAndLanguages;
	const cloudAndBackend = siteContent.about.skills.cloudAndBackend;
</script>

<section id="about-section" class="min-h-screen">
	<SectionHeader sectionTitle={'About me'} />

	<div class="flex h-fit justify-center">
		<div class="bg-[#111f3b] w-8/12 rounded-[35px] shadow-2xl">
			<div class="flex p-8">
				<div
					class="w-3/5 flex flex-col items-center justify-center text-justify text-[#7d8092] p-8">
					<span class="w-full text-justify text-xl font-semibold"
						>{greeting}<br /><br /></span>
					{description}
				</div>
				<div class="w-2/5 flex items-center justify-center">
					<img
						class="h-4/5 rounded-full object-cover aspect-square"
						src="https://static.vecteezy.com/system/resources/previews/002/002/403/original/man-with-beard-avatar-character-isolated-icon-free-vector.jpg"
						alt="Rounded avatar" />
				</div>
			</div>
			<div
				class="h-fit bg-[#1f2937] rounded-[35px] py-16 px-8 flex my-divide-x">
				<div class="w-1/4 flex flex-col items-center">
					<div class="pb-5">
						<div
							class="w-16 h-16 rounded-full bg-[#4069e9] text-white flex items-center justify-center">
							<img src={webIcon} alt="" />
						</div>
					</div>
					<h1 class="pb-10 text-2xl text-[#ced6f5] font-medium">Web</h1>
					{#each webSkills as skill}
						<p class="py-1">{skill}</p>
					{/each}
				</div>
				<div class="w-1/4 flex flex-col items-center">
					<div class="pb-5">
						<div
							class="w-16 h-16 rounded-full bg-[#4069e9] flex items-center justify-center">
							<img src={mobileIcon} alt="" />
						</div>
					</div>
					<h1 class="pb-10 text-2xl text-[#ced6f5] font-medium">Mobile</h1>
					{#each mobileSkills as skill}
						<p class="py-1">{skill}</p>
					{/each}
				</div>
				<div class="w-1/4 flex flex-col items-center">
					<div class="pb-5">
						<div
							class="w-16 h-16 rounded-full bg-[#4069e9] flex items-center justify-center text-center">
							<img src={serverIcon} alt="" />
						</div>
					</div>
					<h1 class="pb-10 text-2xl text-[#ced6f5] font-medium">
						Backend/Cloud
					</h1>
					{#each cloudAndBackend as cloudAndBackendTool}
						<p class="py-1">{cloudAndBackendTool}</p>
					{/each}
				</div>
				<div class="w-1/4 flex flex-col items-center">
					<div class="pb-5">
						<div
							class="w-16 h-16 rounded-full bg-[#4069e9] text-white flex items-center justify-center text-center">
							<img src={terminalIcon} alt="" />
						</div>
					</div>
					<h1 class="pb-10 text-2xl text-[#ced6f5] font-medium">
						Tools/Languages
					</h1>
					{#each toolsAndLangs as toolOrLang}
						<p class="py-1">{toolOrLang}</p>
					{/each}
				</div>
			</div>
		</div>
	</div>
</section>

<style>
	.my-divide-x > * + * {
		border-right-width: 0px;
		border-left-width: 1px;
		border-color: #353e4b;
	}
</style>
