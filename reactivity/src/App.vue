<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Product/>
    <ProductReview />
  </div>
</template>

<script>
import Product from './components/Product.vue'
import ProductReview from './components/ProductReview.vue'

export default {
  name: 'App',
  components: {
    Product,
    ProductReview,
  },
  data() {
    return{

    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
