<template>
  <div class="row">
    <div v-for="(item, index) in items" :key="index" class="col-md-4 pb-4">
      <div class="card" >
        <img :src="item.photo" class="card-img-top bg-primary" alt="product_image">
        <div class="card-body">
          <h5 class="card-title">{{item.title}}</h5>

          <a @click="addToCart(item)" class="btn btn-primary text-left">add to cart</a>
           <p class="text-right m-1 d-inline-flex  ">price-$ {{item.price}}</p>
        </div>
      </div>

    </div>

  </div>
</template>

<script>
    export default {
        name: "Invantory",
        props:['items'],
        methods:{
            addToCart(item){
                this.$emit('newItemAdded',item)
            }
        }
    }
</script>

<style scoped>
  img{
    width: 100%;


  }
  p{
    border: 2px solid mediumvioletred;
    padding: 4px 2px;
    border-radius: 5px;
    background: lightgrey;

  }
</style>
