<script lang="ts">
	import { page } from '$app/stores';
	import { onMount } from 'svelte';
	import SongCardContainer from './SongCardContainer.svelte';

	/* TODO fix song type */
	let songResults: any[] = [];
	let searchResults = 0;
	const searchTerm = $page.params.searchTerm;

	onMount(async () => {
		const itunesSearchData = await fetch(
			`https://itunes.apple.com/search?term=${searchTerm}&entity=song`
		);
		const { resultCount, results } = await itunesSearchData.json();
		songResults = results;
		searchResults = resultCount;
	});
</script>

<h2>Results</h2>
{#if searchResults}
	<SongCardContainer {songResults} />
{/if}
