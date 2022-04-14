<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="info">
        <h1>STATE:</h1>
        <h2>{{product.state}}</h2>
        <h1>CAPITAL:</h1>
        <h2>{{product.city}}</h2>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    products: Array
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


.info {
  background: rgb(109, 109, 247);
  color: #000;
  padding: 10px 30px;
  height: 150px;
}

.info h1 {
  font-size: 10px;
}


.info h2 {
  margin: 0px;
  font-size: 15px;
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
