<script lang="ts">
	import { goto } from '$app/navigation';

	let searchTerm = '';

	function handleSearch() {
		goto(searchTerm);
	}
</script>

<h2>myTunez Search</h2>
<form on:submit|preventDefault={handleSearch} >
	<label>
		Search artist, group or song
		<input type="text" bind:value={searchTerm} />
	</label>
	<button type="submit">Search</button>
</form>

<style>
	h2 {
		font-size: 2.25rem;
	}
	label {
		font-size: 1.25rem;
	}
</style>