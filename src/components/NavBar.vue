<script>
import NavItem from './NavItem.vue'

export default {
    data() {

    }, 
    components: {
        NavItem,
    }
}
</script>

<template>
    <main>
        <NavItem>
            <img alt="Vue logo" class="logo" src="../assets/logo.svg" width="125" height="125" />
            <a href="/" rel="noopener">pictureofhotdog.com</a>
        </NavItem>
        <NavItem>
            <a href="/" rel="noopener">Home</a>
        </NavItem>

        <NavItem>
            <a href="#/about" rel="noopener">About</a>
        </NavItem>

        <NavItem>
            <a href="#/testimonials" rel="noopener">Testimonials</a>
        </NavItem>

        <NavItem>
            <a href="#/statistics" rel="noopener">Statistics</a>
        </NavItem>
    </main>
</template>

<style>

a,
.green {
    margin-bottom: 0.4rem;
    font-size: 1.2rem;
    text-decoration: none;
    color: hsla(160, 100%, 37%, 1);
    transition: 0.4s;
}

@media (min-width: 1024px) {
    main {
        display: flex;
        align-items: center;
        justify-content: space-around;
    }

    .logo {
        margin: 0 2rem 0 0;
    }

}
</style>
