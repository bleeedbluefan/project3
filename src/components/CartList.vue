<template>
    <div class="wrapper">
        <div class="products">
            <div v-if="this.$root.$data.cart.length == 0">
                <p>You Know NO State Capitals</p>
            </div>
            <div v-else class="product" v-for="product in this.$root.$data.cart" :key="product.id">
                <div class="info">
                    <h1>{{product.product.state}}</h1>
                    <h2>{{product.product.city}}</h2>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

// STANDARD EXPORT: 'name' is what it's called / 'props' is the data object transferred
export default {
    name: 'CartList',
    props: {
        products: Array
    },
    methods: {
    }
}
</script>

<style scoped>
.wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
}

.products {
    margin-top: 20px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.product {
    margin: 10px; 
    margin-top: 50px;
    width: 200px;
}

.product img {
    border: 2px solid #333;
    height: 250px;
    width: 200px;
    object-fit: cover;
}

.product .image {
    display: flex;
    justify-content: center;
    margin-bottom: 5px;
}

.info {
    background: rgb(109, 109, 247);
    color: #000;
    padding: 10px 30px;
    height: 80px;
}

.info h1 {
    font-size: 15px;
}

.info h2 {
    font-size: 10px;
}

.info p {
    margin: 0px;
    font-size: 10px;
}


.price {
    display: flex;
}

button {
    height: 50px;
    background: #000;
    color: white;
    border: none;
}

.auto {
    margin-left: auto;
}
</style>