<!--TODO: HEADER -->
<main>
	<slot />
</main>

<!--TODO: FOOTER -->
<style>
	:global(*) {
		box-sizing: border-box;
	}
	:global(p, b, h1, h2, label, a) {
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell,
			'Open Sans', 'Helvetica Neue', sans-serif;
		color: #101010;
	}

	main {
		max-width: 968px;
		margin: 1rem auto;
	}
</style>
