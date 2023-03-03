<script>
import NavBar from './NavBar.vue'

export default {
    data() {
        return {
            hotdog: "default",
            numDresses: 0,
        }
    },
    components: { NavBar },
}
</script>

<template>
    <body>
        <NavBar></NavBar>

    </body>
    This is the About page. The hot dog is {{ hotdog }}. 
    You've dresssed the dog {{  numDresses }} times.
</template>

<style scoped></style>
