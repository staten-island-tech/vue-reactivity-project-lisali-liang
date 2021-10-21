<template>
  <div id="app">
    <h1>shopping site</h1>
    <h1>{{ text }}</h1>
    <div class="item item-one">
      <h1>This is an item</h1>
      <img :src="image" />
      <p v-if="inventory > 50">In Stock</p>
      <p v-else>Out of Stock</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      text: "text",
      image:
        "https://images.unsplash.com/photo-1514897575457-c4db467cf78e?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
      inventory: 100,
      details: [],
    };
  },
};
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
