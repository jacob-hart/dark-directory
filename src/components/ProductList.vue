<template>
<div class="row d-flex justify-content-center mt-3">
  <div class="product" v-for="product in products" :key="product.id">
    <div v-if="product.dark == 0">
      <div class="card border-danger bg-dark m-3" style="width: 15rem;">
        <div class="card-body">
          <h5 class="card-title text-light mb-2">{{product.name}}</h5>
          <h6 class="card-text mb-2 text-danger btn btn-outline-danger py-1 px-2">No.</h6>
          <br>
          <router-link :to="'/product/' + product.id" class="card-text text-light stretched-link">{{product.context.slice(0, 40).trim() + "..."}}</router-link>
        </div>
      </div>
    </div>
    <div v-else-if="product.dark == 1">
      <div class="card border-success bg-dark m-3" style="width: 15rem;">
        <div class="card-body">
          <h5 class="card-title text-light mb-2">{{product.name}}</h5>
          <h6 class="card-text mb-2 text-success btn btn-outline-success py-1 px-2">Yes!</h6>
          <br>
          <router-link :to="'/product/' + product.id" class="card-text text-light stretched-link">{{product.context.slice(0, 40).trim() + "..."}}</router-link>
        </div>
      </div>
    </div>
    <div v-else-if="product.dark == 2">
      <div class="card border-warning bg-dark m-3" style="width: 15rem;">
        <div class="card-body">
          <h5 class="card-title text-light mb-2">{{product.name}}</h5>
          <h6 class="card-text mb-2 text-warning btn btn-outline-warning py-1 px-2">Yes, but...</h6>
          <br>
          <router-link :to="'/product/' + product.id" class="card-text text-light stretched-link">{{product.context.slice(0, 40).trim() + "..."}}</router-link>
        </div>
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
  },
}
</script>