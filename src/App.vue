<template>
  <header class="top-bar spread">
    <nav class="top-bar-nav">
      <router-link to="/" class="top-bar-link">
        <span>Products</span>
      </router-link>
    </nav>
    <div @click="toggleSidebar" class="top-bar-cart-link">
      <i class="icofont-cart-alt icofont-1x"></i>
      <span>Cart ({{ totalQuantity }})</span>
    </div>
  </header>
  <router-view :inventory="inventory" :addToCart="addToCart" />
  <Sidebar 
  v-if="showSideBar" :toggle="toggleSidebar" :cart="cart" :inventory="inventory"
  :remove="removeItem"/>
</template>

<script>
import Sidebar from '@/components/Sidebar.vue'
import product from './data.json'

export default {
  components: {
    Sidebar
  },
  data() {
    return {
      showSideBar: false,
      inventory: product,
      cart: {},
    }
  },
  computed: {
    totalQuantity() {
      return Object.values(this.cart).reduce((acc, curr) => {
        return acc + curr
      },0)
    }
  },
  methods: {
    addToCart(product, quantity) {
      if(!this.cart[product]) this.cart[product] = 0
      this.cart[product] += quantity
      // console.log(this.cart)
    },
    toggleSidebar() {
      this.showSideBar = !this.showSideBar
    },
    removeItem(product) {
      delete this.cart[product]
    }
  }
}
</script>

<style>

</style>
