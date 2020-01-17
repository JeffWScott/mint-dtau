<script>
	import Nav from './Nav.svelte';

	let inputField;
	let vk = "";
	let amount = 100000;
	$: buttonName = "mint"
	$: placeholder = "Lamden Public Address"

	function mint(){
		if (vk === "") {
			inputField.setCustomValidity("I refuse to mint valuable Test TAU to nobody!");
			inputField.reportValidity();
			return
		}
		let body = JSON.stringify({vk, amount})

		fetch("https://testnet.lamden.io/mint", {
            method: 'POST',
            body 
        })
			.then(res => done(res))
            .catch(err => done(err));
	}

	function done(res){
		vk = ""
		placeholder = "Minted 100,000 Test TAU!"
		buttonName = "Done!"
	}

	function changeButtonName(){
		inputField.setCustomValidity("");
        inputField.reportValidity();
		placeholder = "Lamden Public Address"
		buttonName = "mint"
	}
</script>

<style>
	main {
		display: flex;
		flex-direction: column;
		text-align: center;
		justify-content: center;
		align-items: center;
		height: 100%;
		width: 100%;
	}

	h1 {
		color: #461BC2;
		font-size: 2em;
		font-weight: 400;
	}

	a{
		margin-top: 10px;
	}

	button {
		margin: 0 0 0 -1px;
		padding-right: 20px;
		padding-left: 20px;
		border-radius: 0 5px 5px 0;
	}

	.address-row{
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		padding: 0 10px;
		box-sizing: border-box;
		width: 100%;
	}
	.address{
		width: 100%;
		max-width: 600px;
		margin: 0px;
	}
</style>

<Nav />
<main class="main">
	<h1>Mint Me Some Test TAU!</h1>
	<div class="address-row">
		<input bind:this={inputField} class="address" type="text" bind:value={vk} placeholder={placeholder} on:keyup={changeButtonName}/>
		<button on:click={mint}>{buttonName}</button>
	</div>

		<a class="link" href="https://chrome.google.com/webstore/detail/lamden-wallet-browser-ext/lgkgmnhecgdjiifepobmobkeeeheakko"
		rel="noopener noreferrer"
		target="_blank">
			GET Lamden Wallet
		</a>

</main>