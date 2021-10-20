<template>
    <div id="item">
        <img src="" alt="">
        <h1>{{itemName}}</h1>
    </div>
</template>

<script>
export default {
    name: 'Item',
    components: {
    
  },
  props: {
      itemName: String,
  },
  data() {
    return{
      
    }
  }
}
</script>