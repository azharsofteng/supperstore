<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <a class="navbar-brand" href="#">SupperStor</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse float-right" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
        </ul>
        <form @submit.prevent="search" class="form-inline my-2 my-lg-0 ">
          <input class="form-control mr-sm-2 float-right" type="search" placeholder="Search" aria-label="Search" v-model="keyword">
          <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
        </form>
      </div>
    </nav>
</template>

<script>

export default {
 data(){
   return{
      keyword: ''
   }
 },
 methods:{
   search(){
     this.$emit('Search', this.keyword)
   }
 }
}
</script>

<style>

</style>