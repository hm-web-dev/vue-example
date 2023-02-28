<script>
import NavBar from './components/NavBar.vue'

import Home from './components/Home.vue'
import About from './components/About.vue'
import Testimonials from './components/Testimonials.vue'
import NotFound from './components/NotFound.vue'

// very simple router
const routes = {
  '/': Home,
  '/about': About,
  '/testimonials': Testimonials,
}

export default {
  data() {
    return {
      currentPath: window.location.hash
    }
  },
  components: {
    NavBar,
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || NotFound
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
      console.log(window.location.hash);
      this.currentPath = window.location.hash
    })
  }

}
</script>


<template>
  <component :is="currentView" />
</template>

<style scoped></style>
