<template>
  <ul class="product-listing">
    <li v-for="product in allProducts" :key="product.id">
      {{ product.title }} | {{ product.price }}
    </li>
  </ul>
</template>

<script>
import { mapActions, mapGetters } from "vuex"

export default {
  name: "Products",
  methods: {
    ...mapActions(["getProducts"]),
  },
  computed: mapGetters(["allProducts"]),
  created() {
    this.getProducts()
  },
}
</script>

<style scoped></style>
