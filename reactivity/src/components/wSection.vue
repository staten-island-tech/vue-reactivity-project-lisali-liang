<template>
  <div id="wSection">
    <h1>APPAREL</h1>

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
  name: "wSection",
  components: {},

  data() {
    return {
      items: [
        {
          selectedItem: 0,
          itemName: "MA NO. 557 REFLECTIVE SHIRT",
          itemID: 557,
          inventory: 10,
          details: ["M/L/XL", "WHITE/BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01pyZLfg1CJylEzKAbF__39600061-0-lubanu-s_1080x.jpg?v=1589687312)",
          },
          inStock: true,
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 532 REFLECTIVE SHIRT",
          itemID: 532,
          inventory: 500,
          details: ["20% polyester", "Gender-neutral"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01oXbOxc1CJykeeHUPf__39600061_1080x.jpg?v=1588387196)",
          },
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 521 OVERSIZED SHIRT",
          itemID: 521,
          inventory: 25,
          details: ["M/L/XL/2XL", "WHITE/BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01oATjvm1CJykSeNeDv__39600061_1080x.jpg?v=1584788634)",
          },
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 2260 COLLARED SWEATER",
          itemID: 2260,
          inventory: 25,
          details: ["M/L/XL/2XL", "GRAY/BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01At9NXG1CJyqqFt2Pn__39600061_cb1cdcc7-548e-4cab-bba0-5094cfbab79d_1080x.jpg?v=1626263240)",
          },
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 645 HALF ZIP SWEATER",
          itemID: 645,
          inventory: 205,
          details: ["M/L/XL/2XL", "OFF WHITE/BLUE/GRAY"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01UKQ7xM1CJyrgvVJ6C__39600061_1080x.jpg?v=1632981743)",
          },
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 1052 STRAIGHT SWEATPANTS",
          itemID: 1052,
          inventory: 105,
          details: ["S/M/L/XL", "BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01Q4S5Fy26L08wtEXXO__4089117644-0-lubanu-s_1080x.jpg?v=1598483201)",
          },
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 1446 WIDE DENIM JEANS",
          itemID: 1446,
          inventory: 95,
          details: ["M/L/XL/2XL", "BLUE"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01VGxLvC1CJyp2SWe4I__39600061_1080x.jpg?v=1617481069)",
          },
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 1715 LINEN SHORTS",
          itemID: 1715,
          inventory: 105,
          details: ["M/L/XL/2XL", "KHAKI/BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01YZ128K1CJypuXPZ51__39600061_1080x.jpg?v=1625799612)",
          },
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 236 PUFFER JK",
          itemID: 236,
          inventory: 305,
          details: ["M/L/XL/2XL", "GRAY/BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01JBZF791CJyjL5tBXC__39600061_1080x.jpg?v=1623299989)",
          },
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 1091 ZIP UP HOODIE",
          itemID: 1081,
          inventory: 106,
          details: ["M/L/XL/2XL", "GRAY/BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01FIJ4c21CJymplHktL__39600061_1080x.jpg?v=1603161337)",
          },
        },
        {
          inStock: true,
          selectedItem: 0,
          itemName: "MA NO. 1148 LEATHER JK",
          itemID: 1091,
          inventory: 26,
          details: ["M/L/XL/2XL", "BLACK"],
          coverImage: {
            backgroundImage:
              "url(https://cdn.shopify.com/s/files/1/0236/8779/0656/products/O1CN01fIrdMi1CJymRX7u4c__39600061-0-lubanu-s_1080x.jpg?v=1600494037)",
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
  text-decoration: underline;
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
