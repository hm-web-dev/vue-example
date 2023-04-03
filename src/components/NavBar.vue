<script>
import NavItem from './NavItem.vue'

export default {
    components: {
        NavItem,
    }
}
</script>

<template>
    <body>
        <main>
            <NavItem>
                <img alt="Vue logo" class="logo" src="../assets/logo.svg" width="25" height="25" />
                <a href="/#/" rel="noopener">pictureofhotdog.com</a>
            </NavItem>
            <NavItem>
                <a href="/#/" rel="noopener">Home</a>
            </NavItem>
            
            <NavItem>
                <a href="/#/about" rel="noopener">About</a>
            </NavItem>
            
            <NavItem>
                <a href="/#/testimonials" rel="noopener">Testimonials</a>
            </NavItem>
            
            <NavItem>
                <a href="/#/statistics" rel="noopener">Statistics</a>
            </NavItem>
        </main>
        <div class="end">

            <NavItem>
                <a href="/#/cart" rel="noopener">Cart</a>
            </NavItem>
        </div>
        
        </body>
</template>

<style scoped>

a,
.green {
    margin-bottom: 0.4rem;
    font-size: 1.2rem;
    text-decoration: none;
    color: hsla(160, 100%, 37%, 1);
    transition: 0.4s;
}

@media (min-width: 1024px) {
    body {
        display: flex;
        align-items: center;
        justify-content: space-between; /* end and start */
    }

    main, .end { 
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .logo {
        margin: 0 2rem 0 0;
    }

}
</style>
