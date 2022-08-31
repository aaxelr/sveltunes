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
		display: grid;
		grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
	}
</style>
