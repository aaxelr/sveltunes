<script lang="ts">
	import SongCard from './SongCard.svelte';

	export let songResults: any[];
</script>

<div>
	{#each songResults as song}
		<SongCard {song} />
	{/each}
</div>

<style>
	div {
		max-width: 90vw;
		margin: 0 auto;
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 1rem;
	}

	@media screen AND (max-width: 960px) {
		div {
			grid-template-columns: repeat(2, 1fr);
		}
	}
	@media screen AND (max-width: 650px) {
		div {
			grid-template-columns: 1fr;
		}
	}
</style>
