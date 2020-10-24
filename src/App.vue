<template>
  <div id="app">
    <Navbar></Navbar>
    <div class="container">
        <div class="row">
          <div class="col-sm-9 mt-2">
              <Inventory :items="items"></Inventory>
          </div>
          <div class="col-sm-3 mt-2">
              <Cart></Cart>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import Cart from './components/Cart'
import Inventory from './components/Inventory'
import data from './data.js'

export default {
  components:{
    Navbar,
    Cart,
    Inventory
  },
  data(){
    return{
      items: []
    }
  },
  mounted(){
    this.items = data
  }
}
</script>

<style>
#app {
  
}
</style>
