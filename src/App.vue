<template>
  <div id="app">

<navbar @search="search"></navbar>

    <div class="container pt-5">
      <div class="row">
        <div class="col-md-9">
         <inventory @newItemAdded ="addCartItem"  :items="items"></inventory>
         </div>
        <div class="col-md-3">
            <cart @removeItem="ItemRemove"  :items="cart"></cart>

        </div>
      </div>
    </div>

</div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import navbar from './components/Navbar'
import inventory from './components/Invantory'
import cart from './components/Cart'
import data from "./data";
export default {
    components:{
        navbar,
        inventory,
        cart
    },
      data(){
      return{
        items:[],
          cart:[]

      }
      },
    mounted() {
        this.items = data
  },
    methods:{
        search(keyword){
            this.items = data.filter(item =>{
                return  item.title.toLowerCase().indexOf(keyword.toLowerCase()) !== -1
            })

        }
        ,
     addCartItem(item){
      this.cart.push(item)
     },
        ItemRemove(index){
         this.cart.splice(index,1)
        }

    }
}
</script>

<style>

</style>
