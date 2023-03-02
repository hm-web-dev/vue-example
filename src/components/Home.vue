<script>
import NavBar from './NavBar.vue'

export default {
    data() {
        const otherDogs= [
                {
                    src: "https://images.squarespace-cdn.com/content/v1/5dd8630d09ab5908e35b35a0/1574462664001-48S1VO61L9LNWNJ910CV/img-HotDogStock-1080x675.png?format=1000w",
                    hotdog: "default"
                },
                {
                    src: "https://images.squarespace-cdn.com/content/v1/5dd8630d09ab5908e35b35a0/1575408711651-9RQZJE8ZI0BV3Y1CV0LN/hot+dog+wiht+must.jpg?format=1000w",
                    hotdog: "mustard"
                },
                {
                    src: "https://images.squarespace-cdn.com/content/v1/5dd8630d09ab5908e35b35a0/1582497960940-IAE86F3OGQKE0D19GGYA/ketchup+dog.jpg?format=1000w",
                    hotdog: "ketchup"
                }
            ];
            const res = otherDogs.find(h => h.hotdog == this.hotdog);
            console.log(res);
        return {
            hotdog: this.hotdog,
            src: res.src,
            otherDogs: otherDogs,
        }
    },
    emits: ['changeData'],
    methods: {
        changeData(hotdog) {
            this.src = hotdog.src;
            this.$emit('changeData', hotdog.hotdog);
        }
    },
    props: {
        hotdog: String
    },
    components: { NavBar },
}
</script>

<template>
    <header>
        <NavBar></NavBar>
    </header>

    <body>
        <img :src="src" alt="hotdog">
        <div class="links">
            <!-- do you think you could wrap this better?-->
            <a v-on:click="e => changeData(otherDogs[1])">
                Put some {{ otherDogs[1].hotdog }} on it
            </a>

            <a v-on:click="e => changeData(otherDogs[2])">
                Put some {{ otherDogs[2].hotdog }} on it
            </a>
        </div>
    </body>
</template>

<style scoped>
img {
    display: block;
    margin-left: auto;
    margin-right: auto;
}

.links {
    display: flex;
    justify-content: space-evenly;
}
</style>
