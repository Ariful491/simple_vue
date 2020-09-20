<template>
  <ul class="list-group">
    <li class="list-group-item">
      <h4>Cart - total </h4>
    </li >
    <li v-for="(item, index) in items" :key="index" class="list-group-item">
      <button @click="removeItem(index)" class="btn btn-danger btn-sm float-left">-</button>
    <h6 class="float-right">{{item.title}} - {{item.price}}</h6>
    </li>
    <li class="list-group-item">
    <h4>Total -$ {{totalPrice}}</h4>
  </li>
  </ul>
</template>

<script>
    export default {
        name: "Cart",
        props:['items'],
        computed:{
            totalPrice(){
               var total = 0;
              this.items.forEach(item  => {
                total += parseFloat(item.price)
              })
                return total
            }
        },
        methods:{
            removeItem(index){
                  this.$emit('removeItem',index)
            }
        }
    }
</script>

<style scoped>

</style>
