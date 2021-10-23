<script>
    import ProductCard from "./products-card.svelte"

    export let selectedCatagory

    let fetchImage = (async () => {
		let response = await fetch('https://fakestoreapi.com/products')
    return await response.json()
	})()
    

</script>
<div class="products">
{#await fetchImage}
	<p>...waiting</p>
{:then data}
  {#if selectedCatagory == "All products"}
	{#each data as product, index}
       <ProductCard product={product}/>
  {/each}
  {:else}
    {#each data as product, index}
       {#if product.category == selectedCatagory}
       <ProductCard product={product}/>
       {/if}
    {/each}
  {/if}
  
{:catch error}
	<p>An error occurred!</p>
{/await}
</div>


<style>
.products{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  justify-items: center;
}

</style>