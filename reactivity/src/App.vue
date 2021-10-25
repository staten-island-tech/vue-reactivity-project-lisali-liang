<template>
  <div id="app">
    <h1 class="name">meilleur avant</h1>
    <div class="navigation">
      <h3>women</h3>
      <h3>men</h3>
      <h3>accessories</h3>
    </div>

    <img class="banner-image" :src="bannerImage" alt="Banner" />
    <div class="item item-one">
      <img class="product-image" :src="imageOne" alt="Image One" />
      <div class="item-details">
        <h1>This is an item</h1>
        <p v-if="inventory > 50">In Stock</p>
        <p v-else>Out of Stock</p>
        <ul>
          <li v-for="detail in details" :key="detail">{{ detail }}</li>
        </ul>
      </div>
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
      bannerImage:
        "https://images.unsplash.com/photo-1546213290-e1b492ab3eee?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1374&q=80",
      imageOne:
        "https://images.unsplash.com/photo-1564859227552-81fde4a1df0b?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTZ8fHQlMjBzaGlydHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=60",
      inventory: 100,
      details: ["80% cotton", "20% polyester", "Gender-neutral"],
    };
  },
};
</script>

<style>
:root {
  --image-size: 400px;
}

@import url("https://fonts.googleapis.com/css2?family=Cardo:wght@700&display=swap");

#app {
  font-family: "Cardo", serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #001326;
  margin: 0;
  max-width: 100vw;
}

div {
  margin: 50px;
}

.name {
  font-size: 40px;
  letter-spacing: 25px;
  /* background-color: blue; */
}

.navigation {
  /* background-color: red; */
  display: flex;
  justify-content: space-around;
  margin: 0;
}

.item {
  display: flex;
}

.banner-image {
  width: 90vw;
  height: auto;
}

.product-image {
  height: var(--image-size);
  width: var(--image-size);
}
</style>
