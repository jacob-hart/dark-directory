<template>
<div>
  <!-- <h5>Does</h5> -->
  <input class="form-control form-control-lg" v-model="searchText" autofocus/>
  <!-- <h5>have a dark theme?</h5> -->
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

