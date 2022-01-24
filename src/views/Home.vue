<template>
  <div class="home">
    <main class="wrapper">

      <h2>Products</h2>

      <div class="card-contai">
        <ProductCard v-for="(product, index) in inventory" :key="product.id" class="card" :index="index" :product="product" :addToCart="addToCart" />
      </div>

    </main>
  </div>
</template>

<script>
// @ is an alias to /src
import ProductCard from '@/components/ProductCard.vue'

export default {
  name: "Home",
  props: ['inventory','addToCart'],
  components: {
    ProductCard
  },
};
</script>
