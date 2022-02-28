<script lang="ts">
	import { convertToSlug } from '$utils/convert-to-slug';
	import { flip } from 'svelte/animate';

	export let tag!: string;
</script>

<a
	sveltekit:prefetch
	href="{`/tags/${convertToSlug(tag)}`}"
	aria-label="{tag}"
	class="text-xs text-black-600 bg-blue-200 rounded-full hover:bg-violet-600 hover:bg-purple-700 focus:outline-none focus:ring-2 focus:ring-purple-600 focus:ring-opacity-50 dark:text-gray-300 hover:text-gray-900 dark:hover:text-gray-500"
>
<button class="rounded-full py-2 px-4">
	{tag.toUpperCase()}
	</button>
</a>

