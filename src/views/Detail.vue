<template>
<div>
  <p>{{product.name}}</p>
  <p>{{product.dark}}</p>
  <p>{{product.context}}</p>
  <router-link :to="'/'" class="text-muted">Back</router-link>
</div>
</template>


<script>
export default {
  name: 'Detail',
  computed: {
    product() {
      return this.$root.$data.products[this.$route.params.id - 1]
    }
  },
}
</script>

