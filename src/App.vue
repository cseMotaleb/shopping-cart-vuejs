<template>
<div id="app">
    <Product></Product>

</div>
</template>

<script>
import Product from './components/Product.vue';

export default {
    name: 'App',
    components: {
        Product,
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans - serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;

}
</style>
