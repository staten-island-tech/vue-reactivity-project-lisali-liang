<template>
  <div id="app">
    <div class="header">
      <div class="header-content">
        <h1 class="name" @click="toMain">meilleur avant</h1>
        <div class="navigation">
          <div
            class="section"
            v-for="(page, index) in pages"
            :key="page.pageName"
          >
            <h3 class="section-text" @click="updatePage(index)">
              {{ page.pageName }}
            </h3>
          </div>
        </div>
      </div>
    </div>

    <testing v-show="banner"></testing>

    <wSection
      v-show="wClicked"
      @add-to-cart="addCart"
      @remove-from-cart="removeCart"
    ></wSection>

    <bSection
      v-show="bClicked"
      @add-to-cart="addCart"
      @remove-from-cart="removeCart"
    ></bSection>

    <cSection
      v-show="cClicked"
      @add-to-cart="addCart"
      @remove-from-cart="removeCart"
    ></cSection>

    <div class="footer" v-show="placeOrder">
      <div class="footer-content">
        <h1>Cart {{ cartNumber }}</h1>
        <div class="review" v-show="cart.length > 0">
          <h3>Review your Order</h3>
          <div class="class-container">
            <div class="cart-list" v-for="cartItems in cart" :key="cartItems">
              <p class="list-item">No. {{ cartItems }}</p>
            </div>
          </div>
          <button @click="confirm">Confirm</button>
        </div>
      </div>
    </div>
    <div class="footer footer-new" v-show="order">
      <div class="footer-content">
        <h1>Order Received</h1>
        <p>
          Thank you for shopping at meilleur avant. <br />Please refresh to
          place another order.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import wSection from "./components/wSection.vue";
import bSection from "./components/bSection.vue";
import cSection from "./components/cSection.vue";
import testing from "./components/testing.vue";

export default {
  name: "App",
  components: {
    wSection,
    cSection,
    bSection,
    testing,
  },
  data() {
    return {
      banner: true,
      wClicked: false,
      bClicked: false,
      cClicked: false,
      order: false,
      placeOrder: true,
      cart: [],
      cartNumber: 0,
      text: "text",
      bannerImage:
        "https://images.unsplash.com/photo-1546213290-e1b492ab3eee?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1374&q=80",

      pages: [
        {
          pageName: "apparel",
        },
        {
          pageName: "bags",
        },
        {
          pageName: "accessories",
        },
      ],
    };
  },
  methods: {
    write() {
      console.log("text is being logged");
    },
    isShown() {
      this.random = true;
    },

    addCart(itemID) {
      this.cartNumber += 1;
      console.log("app id" + itemID);
      this.cart.push(itemID);
      console.log(this.cart);
      this.cartNumber = this.cart.length;
    },
    removeCart(itemID) {
      var index = this.cart.indexOf(itemID);
      if (index > -1) {
        this.cart.splice(index, 1);
      }
      this.cartNumber = this.cart.length;
    },
    updatePage(index) {
      if (index == 0) {
        this.wClicked = true;
        this.bClicked = false;
        this.cClicked = false;
        this.banner = false;
      }
      if (index == 1) {
        this.bClicked = true;
        this.wClicked = false;
        this.cClicked = false;
        this.banner = false;
      }
      if (index == 2) {
        this.cClicked = true;
        this.wClicked = false;
        this.bClicked = false;
        this.banner = false;
      }
    },
    toMain() {
      this.banner = true;
      this.wClicked = false;
      this.bClicked = false;
      this.cClicked = false;
    },
    confirm() {
      this.order = true;
      this.placeOrder = false;
    },
  },
};
</script>

<style>
:root {
  --image-size: 350px;
  --my-font: "Cardo", serif;
}

@import url("https://fonts.googleapis.com/css2?family=Cardo:wght@700&display=swap");

h1 {
  font-size: 25px;
}
h3 {
  font-size: 20px;
}
#app {
  font-family: "Cardo", serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #001326;
  margin: 0;
  max-width: 100vw;
}
.header {
  display: flex;
  justify-content: center;
}
.header-content {
  color: white;
  background-color: rgba(0, 0, 0, 0.877);
  width: 90vw;
}
.name {
  font-size: 40px;
  letter-spacing: 25px;
}
.name:hover {
  text-decoration: underline;
}

.navigation {
  margin: 0;
  display: flex;
  justify-content: space-around;
}

.banner-image {
  width: 90vw;
  height: auto;
}

.section-text:hover {
  text-decoration: underline;
}
.footer {
  display: flex;
  justify-content: center;
  color: white;
}
.footer-content {
  background-color: rgba(0, 0, 0, 0.877);
  width: 90vw;
  padding-bottom: 20px;
}

.class-container {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.list-item {
  width: 300px;
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
  background-color: white;
  color: black;
}
</style>
