<template>
  <div id="app">
    <h1>shopping site</h1>
    <h1>{{text}}</h1>
    <div class="item item-one">
      
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
    
  },
  data() {
    return{
      text:"text"
    }
  }
}
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
