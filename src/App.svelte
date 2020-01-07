<script>
	let address
</script>

<main class="main">
	<h1>Mint me some test TAU!</h1>
	<input class="address" type="text" bind:value={address} />

</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 400;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
	.address{
		width: 300px;
	}
</style>