<template>
  <div id="wSection">
    <h1>womens section</h1>

    <div class="items">
      <div class="item item-one">
        <div class="each-item" v-for="item in items" :key="item">
          <h1>{{ item.itemName }}</h1>
          <img class="product-image" :src="item.itemImage" alt="item image" />
          <p v-if="item.inventory > 50">In Stock</p>
          <p v-else>Out of Stock</p>
          <ul>
            <li v-for="detail in item.details" :key="detail">{{ detail }}</li>
          </ul>
          <button>add to cart</button>
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
          itemName: "item one",
          inventory: 10,
          details: ["80% cotton", "20% polyester", "Gender-neutral"],
          itemImage:
            "https://images.unsplash.com/photo-1564859227552-81fde4a1df0b?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTZ8fHQlMjBzaGlydHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=60",
        },
        {
          itemName: "item two",
          inventory: 500,
          details: ["20% polyester", "Gender-neutral"],
          itemImage:
            "https://images.unsplash.com/photo-1529374255404-311a2a4f1fd9?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1469&q=80",
        },
        {
          itemName: "item three",
          inventory: 25,
          details: ["85% cotton", "15% polyester", "Gender-neutral"],
          itemImage:
            "https://images.unsplash.com/photo-1607160199580-1b0c9b736b66?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
        },
        {
          itemName: "item four",
          inventory: 25,
          details: ["85% cotton", "15% polyester", "Gender-neutral"],
          itemImage:
            "https://images.unsplash.com/photo-1607160199580-1b0c9b736b66?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
        },
        {
          itemName: "item five",
          inventory: 205,
          details: ["85% cotton", "15% polyester", "Gender-neutral"],
          itemImage:
            "https://images.unsplash.com/photo-1607160199580-1b0c9b736b66?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1470&q=80",
        },
      ],
    };
  },

  methods: {
    addToCart: function() {},
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
  flex-wrap: wrap;
  background-color: lightblue;
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
