<script lang="ts">
	import { page } from '$app/stores';
	import { onMount } from 'svelte';
import DetailedSongCard from './DetailedSongCard.svelte';

	let trackResult: any;

	onMount(async () => {
		const trackId = $page.params.trackId;
    console.log(trackId)
		const itunesSearchData = await fetch(
			`https://itunes.apple.com/search?term=${trackId}&entity=song`
		);
    const { results } = await itunesSearchData.json();
    trackResult = results[0];
    console.log(trackResult);
    
	});
</script>

{#if trackResult}
  <DetailedSongCard track={trackResult} />
{/if}
