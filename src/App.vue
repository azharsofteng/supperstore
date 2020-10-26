<template>
  <div id="app">
    <Navbar @Search="search"></Navbar>
    <div class="container">
        <div class="row">
          <div class="col-sm-9 mt-2">
              <Inventory @newItemAdd="addCart" :items="items"></Inventory>
          </div>
          <div class="col-sm-3 mt-2">
              <Cart @itemRemove="removeItem" :items="cart"></Cart>
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
      items: [],
      cart: []
    }
  },
  mounted(){
    this.items = data
  },
  methods:{
    search(keyword){
      this.items = data.filter(item=>{
        return item.title.toLowerCase().indexOf(keyword.toLowerCase()) !== -1
      })
    },
    addCart(item)
    {
      this.cart.push(item)
    },
    removeItem(index){
      this.cart.splice(index, 1)
    }
  }
}
</script>

<style>

</style>
