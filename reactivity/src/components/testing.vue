<template>
  <div>
    <img class="banner-image" :src="bannerImage" alt="Banner" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      bannerImage:
        "https://images.unsplash.com/photo-1546213290-e1b492ab3eee?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1374&q=80",
    };
  },
};
</script>
