<script lang="ts">
import { onMount } from 'svelte';
import ResaultCard from './Resault-card.svelte';
export let searchValue: string = "";

onMount(()=>{console.log(searchValue);})

console.log(searchValue);

$:fetchItems = (async () => {
		const response = await fetch(`https://fakestoreapi.com/products/category/${searchValue}`)
    return await response.json()
	})()


</script>


{#await fetchItems}
{:then data}
    <div class="resault-box" > 
        <p>Products</p>
        {#if data.length > 0}
        {#each {length: 3} as item, index}
            <ResaultCard item={data[index]}/>
        {/each}
        {/if}
    </div>
{:catch error}
	<p>An error occurred!</p>
{/await}




<style>
    .resault-box{
        background-color: white;
        position: absolute;
        top: 0;
        z-index: 1;
        width: 100%;
        padding-top: 25px;
        border-radius: 10px;     
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    }

    p{
        padding-top: 25px;
        margin-left:50px;
        margin-right:50px;
        border-bottom: 3px solid rgb(25, 214, 214);
    }
</style>