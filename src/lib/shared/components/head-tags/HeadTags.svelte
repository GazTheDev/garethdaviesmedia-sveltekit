<script lang="ts">
	// Start: Local Imports
	// Components
	import SEO from '../seo/SEO.svelte';
	// Models
	import type { IMetaTagProperties } from '$models/interfaces/imeta-tag-properties.interface';
	// End: Local Imports

	const description =
		'Gareth Davies Is a web developer based in Surrey and Braintree.';

	// Start: Exported Properties
	/**
	 * @type {IMetaTagProperties}
	 */
	export let metaData: Partial<IMetaTagProperties> = {};
	// End: Exported Properties

	metaData = {
		title: metaData.title ? metaData.title : 'Gareth Davies',
		description: metaData.description ? metaData.description : description,
		...metaData,
	};
</script>

<SEO metaData="{metaData}" />
