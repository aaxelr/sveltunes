<script lang="ts">
	import { page } from '$app/stores';
	export let song: any;

	const trackId = song.trackId;
	const fullArtistName = song.artistName;
	const fullTrackName = song.trackName;
	const trunkArtistName =
		fullArtistName.length > 25 ? fullArtistName.substring(0, 25).concat('...') : fullArtistName;
	const trunkTrackName =
		fullTrackName.length > 25 ? fullTrackName.substring(0, 25).concat('...') : fullTrackName;
</script>

<div class="wrapper">
	<img src={song.artworkUrl100} alt="" />
	<div class="inner">
		<b title={fullArtistName}>{trunkArtistName}</b>
		<p title={fullTrackName}>{trunkTrackName}</p>
		<a href={`${$page.params.searchTerm}/${trackId}`}>View more</a>
	</div>
</div>

<style>
	.wrapper {
		border: 1px solid salmon;
		border-radius: 5px;
		display: flex;
		box-shadow: -5px 5px 5px rgba(250, 128, 114, 0.7);
		max-height: 100px;
	}
	img {
		width: 100px;
		height: 100px;
		padding-right: 0.5rem;
	}
	.inner {
		display: inline-flex;
		flex-direction: column;
		align-items: baseline;
		margin-top: 0.5rem;
		max-width: 20rem;
		overflow: hidden;
		white-space: nowrap;
	}
	p {
		margin: 0.5rem 0;
		text-overflow: ellipsis;
	}
</style>
