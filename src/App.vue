<script>

// App is the PARENT COMPONENT of Home. 
import Home from './components/Home.vue'
import Testimonials from './components/Testimonials.vue'
import About from './components/About.vue'
import Cart from './components/Cart.vue'

// hi y'all, going to number the changes so it's clear to you. 

// 1. create a routes object with all your navbar routes
// see https://vuejs.org/guide/scaling-up/routing.html#simple-routing-from-scratch
const routes = {
  '/': Home, 
  '/testimonials': Testimonials, 
  '/about': About, 
  '/cart': Cart,
}

export default {
  data() {
    return {
      hotdog: "default", 
      numDresses: 0,
      currentPath: routes['/'], 
      // 2. change the currentPath to be the value of the routes variable (instead of just a string)
    }
  },
  // this is a very contrived way of listening to child events. 
  methods: {
    someEvent(n) {
      this.hotdog = n;
      this.numDresses++;
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
      // 2. remove the hashtag so we just get the route
      const removeHash = window.location.hash.slice(1);
      // 3. make the currentPath 
      this.currentPath = routes[removeHash || '/'];
    })
  },
  components: {
    Home
  }
}
</script>


<template>
  <!-- 4. change Home to be a dynamic component, and add :is="currentPath" as a directive -->
  <component :is="currentPath" @change-data="someEvent" :hotdog="hotdog" />
  <div class="center">
  You've dressed the dog {{ numDresses }} times!
  </div>
</template>

<style scoped>
.center {
  text-align: center;
}
</style>
