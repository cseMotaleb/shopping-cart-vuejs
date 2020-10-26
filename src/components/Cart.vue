<template>
<div>
    <h1>Your Cart</h1>
    <div class="products">
        <div v-for="(product, index) in cart" :key="index" class="singel-products">
            <img :src="product.image" alt="" />
            <h1>{{ product.name }}</h1>
            <h1>{{ product.price }}</h1>
            <button @click="removeItemToCart(product)">Remove for Cart</button>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: Cart,

}
</script>>
