<script lang="ts" context="module">
	import { browser, dev } from '$app/env';

	// we don't need any JS on this page, though we'll load
	// it in dev so that we get hot module replacement...
	export const hydrate = dev;

	// ...but if the client-side router is already loaded
	// (i.e. we came here from elsewhere in the app), use it
	export const router = browser;

	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<script lang="ts">
	// Start: Local Imports
	// Components
	import HeadTags from '$components/head-tags/HeadTags.svelte';
	import ExternalLink from '$ui/components/external-link/ExternalLink.svelte';
	import ProjectCard from '$components/project-card/ProjectCard.svelte';

	// Models
	import type { IMetaTagProperties } from '$models/interfaces/imeta-tag-properties.interface';
	import type { IProjectCard } from '$models/interfaces/iproject-card.interface';
	// End: Local Imports

	// Start: Local component properties
	/**
	 * @type {IMetaTagProperties}
	 */
	const metaData: Partial<IMetaTagProperties> = {
		title: 'Project | Gareth Davies',
		description: 'My latest projects I have built for clients.',
		url: '/projects',
		keywords: ['sveltekit', 'sveltekit starter', 'sveltekit starter about'],
		searchUrl: '/projects',
	};

	const projects: IProjectCard[] = [
		{
			title: 'Hat-City',
			description:
				'I recently built a website for a client. All he needed was some basic features but a very good design and unique layout',
			slug: 'https://hat-city.co.uk',
			icon: '',
		},
		{
			title: 'BabyBakes',
			description:
				'I recently built a website for a local cake shop in Braintree, Essex. Cassie was brilliant to work for and the end product is brilliant. ',
			slug: 'https://babybakes.co.uk',
			icon: '',
		},
	];

	// End: Local component properties
</script>

<!-- Start: Header Tag -->
<HeadTags metaData="{metaData}" />
<!-- End: Header Tag -->

<!-- Start: Project page section -->
<div class="flex flex-col justify-center items-start max-w-2xl mx-auto mb-16">
	<h1 class="font-bold text-3xl md:text-5xl tracking-tight mb-4 dark:text-white"> Project </h1>
	<div class="mb-8 prose leading-6 text-gray-600 dark:text-gray-400">
		<p>
			Hey, I'm Gareth Davies. I'm a web developer and web designer based in Surrey, England. These are my recent projects
			
		</p>
	</div>
	{#if projects.length > 0}
		{#each projects as project}
			<ProjectCard project="{project}" />
		{/each}
	{/if}
</div>
<!-- End: Project page section -->
