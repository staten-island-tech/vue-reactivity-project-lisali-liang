<template>
  <div id="app">
    <h1 class="name">Lorem ipsum dolor</h1>

    <div class="navigation">
      <div
        class="section"
        v-for="page in pages"
        :key="page.pageName"
        @click="updatePage(page.pageSpecific)"
      >
        <h3>{{ page.pageName }}</h3>
      </div>
    </div>

    <img class="banner-image" :src="bannerImage" alt="Banner" />

    <wSection></wSection>
  </div>
</template>

<script>
import wSection from "./wSection.vue";

export default {
  name: "App",
  components: {
    wSection,
  },
  data() {
    return {
      text: "text",
      bannerImage:
        "https://images.unsplash.com/photo-1546213290-e1b492ab3eee?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1374&q=80",

      moreInfo: ["Store Locator", "Submit Feedback", "Buy Gift Card"],
      wHidden: true,

      pages: [
        {
          pageName: "womens",
          pageSpecific: "./womenSection.vue",
        },
        {
          pageName: "mens",
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
    updatePage(pageSpecific) {
      this.page = pageSpecific;
    },
  },
};
</script>

<style>
:root {
  --image-size: 400px;
}

@import url("https://fonts.googleapis.com/css2?family=Cardo:wght@700&display=swap");

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

.name {
  font-size: 40px;
  letter-spacing: 25px;
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
</style>
