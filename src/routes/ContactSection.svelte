<script lang="ts">
	import siteContent from '$lib/assets/site-content.json';
	import mixpanel from 'mixpanel-browser';

	const contactContent = siteContent.contact;
	const header = contactContent.header;
	const subText = contactContent.subText;

	const fbLink = contactContent.facebook;
	const emailLink = contactContent.email;
	const igLink = contactContent.instagram;
	const linkedInLink = contactContent.linkedIn;
	const githubLink = contactContent.github;

	function openedContactLink(contactType: string) {
		mixpanel.track('Opened contact link', { contactType });
	}
</script>

<section
	id="contact-section"
	class="min-h-screen flex flex-col items-center justify-center px-48">
	<div class="text-center">
		<h1 class="text-6xl font-bold pb-8">{header}</h1>
		<p class="text-xl text-[#737c97] pb-8">{subText}</p>

		<div class="flex justify-center space-x-4">
			<a href={fbLink} target="_blank" rel="noreferrer">
				<button
					type="button"
					on:click={() => openedContactLink('Facebook')}
					class="rounded-full border border-blue-700 text-center p-3 text-[#0b1426] hover:bg-blue-700 hover:text-[#ced6f5]">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="currentColor"
						stroke="#304dc3"
						stroke-width="1"
						stroke-linecap="round"
						stroke-linejoin="round"
						class="feather feather-facebook"
						><path
							d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z" /></svg>
					<span class="sr-only">Icon description</span>
				</button>
			</a>
			<a href={igLink} target="_blank" rel="noreferrer">
				<button
					on:click={() => openedContactLink('Instagram')}
					type="button"
					class="rounded-full border border-blue-700 text-center p-3 text-[#0b1426] hover:bg-blue-700 hover:text-[#ced6f5]">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="currentColor"
						stroke="#304dc3"
						stroke-width="1"
						stroke-linecap="round"
						stroke-linejoin="round"
						class="feather feather-instagram"
						><rect x="2" y="2" width="20" height="20" rx="5" ry="5" /><path
							d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z" /><line
							x1="17.5"
							y1="6.5"
							x2="17.51"
							y2="6.5" /></svg>

					<span class="sr-only">Icon description</span>
				</button>
			</a>
			<a href={linkedInLink} target="_blank" rel="noreferrer">
				<button
					on:click={() => openedContactLink('LinkedIn')}
					type="button"
					class="rounded-full border border-blue-700 text-center p-3 text-[#0b1426] hover:bg-blue-700 hover:text-[#ced6f5]">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="currentColor"
						stroke="#304dc3"
						stroke-width="1"
						stroke-linecap="round"
						stroke-linejoin="round"
						class="feather feather-linkedin"
						><path
							d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z" /><rect
							x="2"
							y="9"
							width="4"
							height="12" /><circle cx="4" cy="4" r="2" /></svg>

					<span class="sr-only">Icon description</span>
				</button>
			</a>
			<a href={githubLink} target="_blank" rel="noreferrer">
				<button
					on:click={() => openedContactLink('Github')}
					type="button"
					class="rounded-full border border-blue-700 text-center p-3 text-[#0b1426] hover:bg-blue-700 hover:text-[#ced6f5]">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="currentColor"
						stroke="#304dc3"
						stroke-width="1"
						stroke-linecap="round"
						stroke-linejoin="round"
						class="feather feather-github"
						><path
							d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22" /></svg>

					<span class="sr-only">Icon description</span>
				</button>
			</a>

			<a
				href={`mailto:${emailLink}?subject=Hi Paolo!`}
				target="_blank"
				rel="noreferrer">
				<button
					on:click={() => openedContactLink('Email')}
					type="button"
					class="rounded-full border border-blue-700 text-center p-3 text-[#0b1426] hover:bg-blue-700 hover:text-[#ced6f5]">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="currentColor"
						stroke="#304dc3"
						stroke-width="1"
						stroke-linecap="round"
						stroke-linejoin="round"
						class="feather feather-mail"
						><path
							d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z" /><polyline
							points="22,6 12,13 2,6" /></svg>

					<span class="sr-only">Icon description</span>
				</button>
			</a>
		</div>
	</div>
</section>

<style>
	section {
		background-color: #0b1426;
		color: #ced6f5;
	}
</style>
