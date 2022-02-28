<script lang="ts">
	// Start: Local Imports
	// Components
	import HeadTags from '$components/head-tags/HeadTags.svelte';
	import ExternalLink from '$ui/components/external-link/ExternalLink.svelte';

	// Models
	import type { IMetaTagProperties } from '$models/interfaces/imeta-tag-properties.interface';
	// End: Local Imports

	// Start: Local component properties
	/**
	 * @type {IMetaTagProperties}
	 */
	const metaData: Partial<IMetaTagProperties> = {
		title: 'About | Gareth Davies',
		description: 'About page of Sveltekit blog starter project',
		url: '/about',
		keywords: ['sveltekit', 'sveltekit starter', 'sveltekit starter about'],
		searchUrl: '/about',
	};
	// End: Local component properties
</script>

<!-- Start: Header Tag -->
<HeadTags metaData="{metaData}" />
<!-- End: Header Tag -->

<!-- Start: About page section -->
<div class="flex flex-col justify-center items-start max-w-2xl mx-auto mb-16">
	<h1 class="font-bold text-3xl md:text-5xl tracking-tight mb-4 text-black dark:text-white"> About Me </h1>
	<div class="mb-8 prose leading-6 text-gray-600 dark:text-gray-400">
		<p>
			Hey, I'm Gareth  I'm a Software Developer, writer and creator of this website. I build fast web applications
		</p>
		<p>
			Hello, thank you for visiting this website. I'm Gareth Davies, a web developer based in Surrey, England. I design websites and build websites using the latest stacks of tech. 
			My day job is Programme Coordinator at PGL Travel ltd but I build and design websites for clients away from my day job. I offer all kinda of websites and packages for clients big and small. 

			I'm a fairly outgoing person who has many hobbies and interests. I'm a keen church bell ringer and have a keen interest in the railway. 
			My blog will feature articles on both subjects alongside some work I have recently completed.
		</p>
	</div>
</div>
<!-- End: About page section -->
