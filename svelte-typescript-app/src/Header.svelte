<script lang="ts">
import Searchbar from "./Search-bar.svelte";
import Catagories from "./Catagory-bar.svelte"
export let value:string 
</script>

<div class="header-top">
    <h1>hotstuff</h1>
    <h6>we might <br> not have the thing</h6>
    <Searchbar />
</div>
<div class="header-bottom">
    <Catagories bind:selectedCatagory={value}/>
</div>

<style>
    .header-top{            
        display: flex;
        align-items: center;
        justify-content: center;

    }
    .header-top > h1 {
        padding: 10px;
        color: rgb(25, 214, 214);
    }
    .header-top > h6{
        padding: 10px;
        color: rgb(25, 214, 214);
    }

</style>