<script lang="ts">
    import Resaultbox from "./Resault-box.svelte";
    let searchValue:string = "";
   
</script>


<div class="wrapper">
<input type="search" autocomplete="off" bind:value={searchValue}  placeholder="Search" name="search" id="search">
{#if searchValue.length > 0}
    <Resaultbox searchValue={searchValue}/>
{/if}
</div>

<style>
   .wrapper{
        height: 50px;
        width: 100%;
        position: relative;
        display: flex;
        align-items: center;
        align-items: flex-start;
       

   }
    input{
        position: relative;
        height: 50px;
        width: 100%;
        border-radius: 100px;
        z-index: 2;
        margin-left:25px;
        margin-right:25px;
        
        
    }

</style>