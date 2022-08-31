<script lang="ts">
	export let track;

	const {
		artistName,
		artworkUrl100,
		collectionName,
		collectionPrice,
		country,
		primaryGenreName,
		releaseDate,
		trackName
	} = track;

	const formatDate = new Date(releaseDate).toLocaleDateString('en-US', {
		year: 'numeric',
		month: 'long',
		day: 'numeric'
	});
</script>

<div class="wrapper">
	<img src={artworkUrl100} alt="WHERE" />
	<h2>{artistName}</h2>
	<p>{trackName}</p>
  <div>
    <p><span>Album:</span> {collectionName}</p>
    <p><span>Price:</span> ${collectionPrice}</p>
    <p><span>Genre:</span> {primaryGenreName}</p>
    <p><span>Country</span> {country}</p>
    <p><span>Release Date:</span> {formatDate}</p>
  </div>
</div>

<style>
  .wrapper {
    margin-top: 4em;
    padding: 2em;
    display: flex;
    flex-direction: column;
    align-items: center;
    border: 1px solid salmon;
    border-radius: 5px;
    box-shadow: -5px 5px 5px rgba(250, 128, 114, 0.7);
  }
  img {
    width: 100px;
    height: 100px;
  }
</style>