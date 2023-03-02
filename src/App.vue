<script>

// App is the PARENT COMPONENT of Home. 
import Home from './components/Home.vue'

export default {
  data() {
    return {
      hotdog: "default", 
      numDresses: 0,
    }
  },
  // this is a very contrived way of listening to child events. 
  methods: {
    someEvent(n) {
      this.hotdog = n;
      this.numDresses++;
    }
  },
  components: {
    Home
  }
}
</script>


<template>
  
  <Home @change-data="someEvent" :hotdog="hotdog" />
  <div class="center">
  You've dressed the dog {{ numDresses }} times!
  </div>
</template>

<style scoped>
.center {
  text-align: center;
}
</style>
