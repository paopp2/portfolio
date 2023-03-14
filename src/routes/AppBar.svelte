<script lang="ts">
	let navBarLinks: string[] = ['Home', 'Portfolio', 'About', 'Contact'];
	let currentNavLink = navBarLinks[0];

	$: getNavBarLinkClass = (navLink: string) => {
		return currentNavLink === navLink
			? 'block py-2 pl-3 pr-4 text-white bg-[#7de1c5] rounded md:bg-transparent md:text-[#7de1c5] md:p-0 dark:text-white'
			: 'block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent';
	};
</script>

<nav class="py-9">
	<div class="container mx-auto flex flex-wrap items-center justify-between">
		<a href="https://flowbite.com/" class="flex items-center">
			<img
				src="https://flowbite.com/docs/images/logo.svg"
				class="mr-3 h-6 sm:h-9"
				alt="Flowbite Logo" />
			<span
				class="self-center whitespace-nowrap text-xl font-semibold dark:text-white"
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
			<ul class="flex flex-row space-x-8">
				{#each navBarLinks as navLink}
					<li>
						<a
							href="#trial"
							class={getNavBarLinkClass(navLink)}
							on:click={() => (currentNavLink = navLink)}
							aria-current="page">{navLink}</a>
					</li>
					""
				{/each}
			</ul>
		</div>
	</div>
</nav>
