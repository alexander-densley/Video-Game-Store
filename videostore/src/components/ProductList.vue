<template>
  <div class="wrapper">
    <div class="products">
      <div class="product" v-for="product in products" :key="product.id">
        <div class="info">
          <h1>{{ product.name }}</h1>
          <p>{{ product.platform }}</p>
        </div>
        <div class="image">
          <img :src="product.image"/>
        </div>
        <div class="price">
          <h2>{{ product.price }}</h2>
          <button v-on:click="addToCart(product)">Add to Cart</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductList",
  props: {
    products: Array,
  },
  methods: {
    addToCart: function (product) {
      let inCart = false;
      for (let index in this.$root.$data.cart) {
        if (this.$root.$data.cart[index].id == product.id) {
          this.$root.$data.cart[index].quantity += 1;
          inCart = true;
          break;
        }
      }
      if (!inCart) {
        product.quantity = 1;
        this.$root.$data.cart.push(product);
      } 
      this.$root.$data.sumItems = 0;
      for (let index in this.$root.$data.cart) {
        this.$root.$data.sumItems += this.$root.$data.cart[index].quantity;
      }
    },
  },
};
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
  background: #f2921d;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
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