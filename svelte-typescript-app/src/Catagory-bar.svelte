<script lang="ts">
    export let selectedCatagory:string = "All products"
    $:console.log(selectedCatagory);
    
	const fetchCategories = (async () => {
		const response = await fetch('https://fakestoreapi.com/products/categories')
    return await response.json()
	})()

</script>

<dir class="catagories">
    <p on:click={()=>{selectedCatagory = "All products"}}>All products</p>
{#await fetchCategories}

{:then data}
	{#each data as Catagory,index}
        <p on:click={(event) =>{selectedCatagory = event.target.innerText}}>{Catagory}</p>
    {/each}

{:catch error}
	<p>An error occurred!</p>
{/await}
</dir>

<style>
.catagories{
    display: flex;
}
p{
    padding-top: 0px;
    margin-top: 0px;
    padding-right: 30px;
    padding-bottom: 10px;
    font-size: large;
    color: white;
}
p:hover{
    color: rgb(230, 171, 9);
    cursor: pointer;
}
</style>