<script lang="ts">
	import Header from "./header.svelte";
	import Products from "./products.svelte";

	let selectedCatagory:string;
	$:console.log(selectedCatagory, "app");
	
</script>

<main>
	<div class="header-wrapper">
	<Header bind:value={selectedCatagory}/>
	</div>
	<Products selectedCatagory={selectedCatagory} />
</main>

<style>
	.header-wrapper{
		padding-left: 11%;
		padding-right: 11%;
        background-color: rgb(10, 82, 82);
	}
</style>