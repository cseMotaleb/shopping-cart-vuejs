<template>
<div>
    <header>
        <button @click="navigateTo('product')">View Products</button>
        <span> in cart <sup>{{ cart.length }}</sup></span>
        <button @click="navigateTo('cart')">View cart</button>
    </header>
    <div v-if="page === 'cart'" class="product-wrapper">
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

    <div v-if="page === 'product'" class="product-wrapper">
        <h1>Products</h1>
        <div class="products">
            <div v-for="product in products" :key="product.name" class="singel-products">
                <img :src="product.image" alt="" />
                <h1>{{ product.name }}</h1>
                <h1>{{ product.price }}</h1>
                <button @click="addItemToCart(product)">Add to Cart</button>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: "cart",
    data: () => {
        return {
            cart: [],
            page: "product",
            products: [{
                    name: "Relish Men Watch",
                    price: "$90.00",
                    image: "https://images-na.ssl-images-amazon.com/images/I/71vKyimxsiL._UX679_.jpg",
                },
                {
                    name: "oppo",
                    price: "$6000.00",
                    image: "https://www.91-img.com/pictures/133188-v4-oppo-f11-mobile-phone-large-1.jpg?tr=q-60",
                },
                {
                    name: "Sun Glass",
                    price: "$20.00",
                    image: "https://static-01.daraz.com.bd/p/21f671837a40db81d2b25edb72fb18f6.jpg",
                },
                {
                    name: "Shoes",
                    price: "$100.00",
                    image: "https://www.target.com.au/medias/static_content/product/images/full/07/18/A1390718.jpg?impolicy=desktop_hero",
                },
            ],
        };
    },
    methods: {
        addItemToCart(product) {
            this.cart.push(product);
            console.log(this.cart);
        },
        navigateTo(page) {
            this.page = page;
        },
        removeItemToCart(product) {
            this.cart.splice(this.cart.indexOf(product))
        }
    },
};
</script>

<style>
body {
    margin: 0px;
    padding: 0px;
}

header {
    background: #ddd;
    padding: 0px;
    text-align: right;
    padding: 20px
}

header span {
    padding: 16px;
    color: blue;
    font-size: 20px;
}

header span sup {
    color: red;
    font-size: 25px;
    font-weight: 700;
}

header h1 {
    margin-right: 20px;
    color: green;
    font: 20px;
}

.products {
    display: grid;
    grid-template-columns: auto auto auto auto;
    grid-template-rows: 300px 300px;
    grid-gap: 10px;
}

.singel-products {
    background: #ddd;

    min-height: 600px;
}

.singel-products img {
    width: 100%;
    height: 400px;
}
</style>
