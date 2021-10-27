<template>
  <div id="wSection">
    <h1>womens section</h1>

    <div class="items">
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
  </div>
</template>

<script>
export default {
  name: "wSection",
  components: {},
  data() {
    return {
      inventory: 100,
      imageOne:
        "https://images.unsplash.com/photo-1564859227552-81fde4a1df0b?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTZ8fHQlMjBzaGlydHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=60",

      details: ["80% cotton", "20% polyester", "Gender-neutral"],
    };
  },
};
</script>

<style>
.items {
  display: flex;
  justify-content: center;
}

.product-image {
  height: var(--image-size);
  width: auto;
}
</style>
