<template>
<div class="wrapper">
  <div class="products">
      <h3 id="correct">You have {{this.$root.$data.cart.length}}/50 Correct!</h3>
    <div class="product" v-for="product in products" :key="product.id">
    <div v-if="checkExist(product)">
      <div class="info">
        <h1>STATE:</h1>
        <h2>{{product.state}}</h2>
        <h1>Do You Know the Capital?</h1>
        <i class="fas fa-search"></i><input v-model="searchText" />
        <button v-bind:id= "product.city" class="checkButton" @click="checkScore(product, searchText)" @>CHECK -></button>

      </div>
    </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'TestView',
  props: {
    products: Array
  },
  methods: {
      checkExist(product) {
        var exists = false;
        for(let i = 0; i < this.$root.$data.cart.length; i++) {
            if (this.$root.$data.cart[i].product == product) {
                exists = true;
            }
        }
        if (exists) {
            return false;
        }   
        else {
            return true;
        }

      },
      checkScore(product, searchText) {
          var test = false;
          var elem = document.getElementById(product.city);
          if (product.city == searchText) {  
                elem.innerHTML = "CORRECT!";
                for(let i = 0; i < this.$root.$data.cart.length; i++) {
                    if (this.$root.$data.cart[i].product == product) {
                        test = true;
                    }
                }
                if (!test) {
                    this.$root.$data.cart.push({product});
                }
                test = false;
                document.getElementById("correct").innerHTML = "You have " + this.$root.$data.cart.length + "/50 Correct!";
                
          }
          else {
              if (elem.innerHTML != "CORRECT!") {
                  elem.innerHTML = "WRONG!";
              }
            
          }
      }

  },
  computed: {

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
  width: 250px;
  
}


.info {
  background: rgb(109, 109, 247);
  color: #000;
  padding: 10px 30px;
  height: 200px;
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

.checkButton {
    margin-top: 15px;
    background-color: grey;
    border: 1px solid black;
}
</style>
