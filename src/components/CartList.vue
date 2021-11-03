<template>
<div class="wrapper">
  <div v-if="products.length === 0">
    <h2>There's nothing in the cart.</h2>
  </div>
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="image">
        <img :src="'/images/products/'+product.image">
      </div>
      <div class="info">
        <h1>{{product.name}}</h1>
        <p>{{product.country}}</p>
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <button @click="removeFromCart(product)" class="auto">Remove</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'CartList',
  props: {
    products: Array
  },
  methods: {
    removeFromCart(item) {
      let index = this.products.indexOf(item);
      this.products.splice(index, 1);
    }
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
  display: grid;
  justify-content: space-around;
}

.product {
  margin: 5px;
  width: 700px;
  display: flex;
  align-items: center;
}

.product img {
  border: 2px solid #333;
  height: 60px;
  width: 60px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
}

.info {
  background: #F2921D;
  color: #000;
  height: 60px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px 10px;
}

.info h1 {
  font-size: 16px;
}

.info p {
  font-size: 10px;
}

.price {
  width: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px 10px;
}

.price h2 {
  padding-right: 10px;
}

button {
  height: 40px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
