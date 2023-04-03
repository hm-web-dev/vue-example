<script>
export default {
    props: ["url", "itemName", "desc", "price"],
    methods: { addToCart() { 
        this.$emit('addToCart', this.itemName, this.price) } }
}
</script>

<template>
    <div class="item">
        <img :src="url" width="300" height="300">
        <h1>Name: {{ itemName }}</h1>
        <h1>Price: ${{ price }}</h1>
        <h1>Description: {{ desc }}</h1>
        <button @click="addToCart()">Add to cart</button>
    </div>
</template>
  
<style scoped>
.item {
    display: flex;
    align-items: center;
    margin-top: 2rem;
    border: 3px solid black;
    height: 400px;
    width: 800px;
    padding-left: 5px;
    padding-right: 5px;
}
</style>