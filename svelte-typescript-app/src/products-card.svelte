<script>
    export let product = {}
</script>

<div class="product-card">
     <img src={product.image} alt="">
     <div class="product-info">
         <h6>{product.title}</h6>
         <p>{product.category}</p>

         <p>{product.price}</p>
    </div>   
</div>
   
<style>
    img{
        width: 150px;
        height: 230px;
 
    }
    .product-card{
        width: 150px;
        
    }
</style>