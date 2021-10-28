<template>
  <div id="wSection">
    <h1>womens section</h1>

    <div class="items">
      <h1>text</h1>
      <h1>text</h1>
      <h1>text</h1>
      <div class="item item-one">
        <div class="item-details">
          <div class="item-names">
            <h1 v-for="item in items" :key="item.itemName">
              {{ item.itemName }}
            </h1>
          </div>

          <div
            class="item-inventory"
            v-for="item in items"
            :key="item.inventory"
          >
            <div class="inventory-details">
              <p v-if="item.inventory > 50">In Stock</p>
              <p v-else>Out of Stock</p>
            </div>
          </div>

          <div class="item-details" v-for="item in items" :key="item.details">
            <ul>
              <li v-for="detail in item.details" :key="detail">{{ detail }}</li>
            </ul>
          </div>

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
      items: [
        {
          itemName: "shirt one",
          inventory: 10,
          details: ["80% cotton", "20% polyester", "Gender-neutral"],
          itemImage:
            "https://images.unsplash.com/photo-1564859227552-81fde4a1df0b?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTZ8fHQlMjBzaGlydHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=60",
        },
        {
          itemName: "shirt two",
          inventory: 500,
          details: ["20% polyester", "Gender-neutral"],
          itemImage:
            "https://images.unsplash.com/photo-1434389677669-e08b4cac3105?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=705&q=80",
        },
      ],
    };
  },
};
</script>

<style>
:root {
  --width: 95vw;
}
.item {
  display: flex;
  justify-content: space-around;
  background-color: blue;
}

.item-names {
  display: flex;
  justify-content: space-around;
  background-color: red;
  width: var(--width);
}
.item-inventory {
  display: flex;
  background-color: purple;
  width: var(--width);
}
.product-image {
  height: var(--image-size);
  width: auto;
}
</style>
