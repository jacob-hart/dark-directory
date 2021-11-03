<template>
<div class="row card-deck mt-3">
  <div class="product" v-for="product in products" :key="product.id">
    <div class="card border-success" style="width: 14rem;">
      <div class="card-body">
        <h5 class="card-title mb-2">{{product.name}}</h5>
        <h6 class="card-text mb-2 text-success">{{product.dark}}</h6>
        <a href="#" class="card-text text-muted stretched-link">{{product.context.slice(0, 40).trim() + "..."}}</a>
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