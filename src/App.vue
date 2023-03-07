<script>

// App is the PARENT COMPONENT of Home. 
import Home from './components/Home.vue'
import Testimonials from './components/Testimonials.vue'

const routes = {
  '/' : Home, 
  '/testimonials': Testimonials 
}
export default {
  data() {
    return {
      hotdog: "default", 
      numDresses: 0,
      currentPath: '/',
    }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/']
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
      this.currentPath = window.location.hash
    })
  },
  // this is a very contrived way of listening to child events. 
  methods: {
    someEvent(n) {
      this.hotdog = n;
      this.numDresses++;
    }
  },
  components: {
    Home, 
    Testimonials
  }
}
</script>


<template>
  <component @change-data="someEvent" :is="currentView" :hotdog="hotdog" />
  <div class="center">
  You've dressed the dog {{ numDresses }} times!
  </div>
</template>

<style scoped>
.center {
  text-align: center;
}
</style>
