<template>
<div>
  <CartList :products="products" />
</div>
</template>

<script>
import CartList from "../components/CartList.vue"
export default {
  name: 'Cart',
  components: {
    CartList
  },
  computed: {
    products() {
      return this.$root.$data.cart;
    }
  },
}
</script>
