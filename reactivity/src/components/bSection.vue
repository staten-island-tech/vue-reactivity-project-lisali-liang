<template>
  <div id="bSection">
    <h1>BAGS</h1>

    <div class="items">
      <div class="item item-one">
        <div class="each-item" v-for="(item, index) in items" :key="item">
          <div class="details">
            <div class="details-cover" :style="item.coverImage"></div>
          </div>
          <div>
            <div class="dropdown">
              <p>{{ item.itemName }}</p>
              <div class="dropdown-content">
                <p
                  class="drop-item"
                  v-for="detail in item.details"
                  :key="detail"
                >
                  {{ detail }}
                </p>
              </div>
              <p v-if="item.inventory > 50">In Stock</p>
              <p v-else-if="(item.inStock = false)">Out of Stock</p>
              <p v-else>Out of Stock</p>
            </div>
            <div class="cart-details" v-show="item.inStock">
              <button
                class="remove"
                @click="removeFromCart(item.itemID, index)"
              >
                remove from cart
              </button>
              <button class="add" @click="addToCart(item.itemID, index)">
                add to cart
              </button>

              <p>{{ item.selected }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "bSection",
  components: {},

  data() {
    return {
      items: [
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 003 SHOULDER BACKPACK",
          itemID: 557,
          inventory: 110,
          details: ["CREAM", "BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01fQ8dD21CJypn78gHh__39600061_1080x.jpg?v=1625961509)",
          },
        },

        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 1248 SHOULDER MESSENGER BAG",
          itemID: 1248,
          inventory: 16,
          details: ["BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01lRFaA61CJyms4GMV1__39600061_1080x.jpg?v=1625961639)",
          },
        },

        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 049 SMALL MESSENGER SHOULDER BAG",
          itemID: 49,
          inventory: 100,
          details: ["BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01iLzAUv1CJys4ehxbJ__39600061_1080x.jpg?v=1634977861)",
          },
        },
      ],
    };
  },

  methods: {
    addToCart(itemID) {
      this.$emit("add-to-cart", itemID);
      console.log(itemID);

      // this.cart.push(itemID);
      // console.log(this.cart);
      // this.cartNumber = this.cart.length;
    },
    removeFromCart(itemID) {
      this.$emit("remove-from-cart", itemID);
      console.log(itemID);
    },

    // breaking my code
  },
  computed: {
    itemDetails() {
      return this.cart;
    },
  },
};
</script>

<style>
:root {
  --width: 75vw;
}
.items {
  display: flex;
  justify-content: center;
}
.item {
  width: 90vw;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.item-names {
  display: flex;
  justify-content: space-around;
  background-color: red;
  width: 60vw;
}
.item-inventory {
  display: flex;
  background-color: purple;
  width: var(--width);
}

.details {
  width: var(--image-size);
  height: var(--image-size);
  border: 1px solid #000000;
  overflow: hidden;
  position: relative;
}
.details-cover {
  width: 100%;
  height: 100%;
  background-size: contain;
  background-position: center;
  transition: all 1s;
}

.details-cover:hover {
  transform: scale(1.2);
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #dfdfdf;
  z-index: 1;
  width: 100%;
}

.dropdown:hover .dropdown-content {
  display: block;
}
.drop-item {
  font-size: 10px;
}

.cart-details {
  padding: 0;
  width: 100%;
}

button {
  border: none;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font: var(--my-font);
  font-size: 13px;
  border-radius: 4px;
  text-transform: uppercase;
}

.add {
  background-color: rgb(4, 0, 37);
  color: white;
}

.remove {
  background-color: white;
  color: black;
}
</style>
