<template>
  <nav class="navbar navbar-expand-sm navbar-light bg-primary ">
    <div class="container">
      <a class="navbar-brand font-weight-bolder" href="#">SimpleCartStore Shop</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <form @submit.prevent="Serach" class="form-inline my-2 my-lg-0 ml-auto">
          <input class="form-control mr-sm-2" v-model="keyword" type="search" placeholder="Search" aria-label="Search">
          <button class="btn btn-outline-warning btn-lg my-2 my-sm-0 font-weight-bolder text-light "  type="submit">Search</button>

        </form>
      </div>
    </div>
  </nav>
</template>

<script>
    export default {
        name: "Navbar",
        data(){
            return{
                keyword:''
            }
        },
        methods:{
            Serach(){
             this.$emit('search',this.keyword)
            }
        }
    }
</script>

<style scoped>

</style>
