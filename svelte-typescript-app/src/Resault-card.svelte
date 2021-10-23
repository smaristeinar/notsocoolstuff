<script lang="ts">
export let item : object = {}
</script>

<div>
    <div>
    <img src="{item.image}" alt="image">
    <h1>{item.title}</h1>
    </div>
    <p>{item.price}$</p>
</div>


<style>
    div{
        display: flex;
        padding-left:50px;
        padding-top: 10px;
   
        flex-direction: row;
        justify-content: space-between;
    }

    h1{
        font-size: 20px;
    }
    img{
        width: 100px;
        height: 100px;
        padding-right: 25px;
        padding-bottom: 10px;
    }
    p{
        padding-right: 200px;   
    }


</style>