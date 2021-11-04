<template>
<div>
  <div class="d-flex justify-content-center align-items-center">
    <h4 class="mr-3 mt-1 text-light text-nowrap font-weight-normal">Does</h4>
    <input class="form-control form-control-lg bg-dark text-light border-muted w-25" v-model="searchText" autofocus/>
    <h4 class="ml-3 mt-1 text-light text-nowrap font-weight-normal">have a dark theme?</h4>
  </div>
  <ProductList :products="products" />
</div>
</template>


<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Home',
  components: {
    ProductList
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.name.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
    }
  },
}
</script>

<style>
  .form-control:focus {
        border-color: #ced4da;
        box-shadow: 0 0 0.25rem 0.25rem rgba(255, 255, 255, 0.25);
  } 
</style>