<template>
  <div class="container">
    <h1>CSR Products</h1>
    <NavLinks />
    <p><strong>Notice</strong> when you click the card, how the Product details (green background) is already rendered when the page loads while the Review cards (red background) takes time to render</p>

    <ProductCards v-if="products" :products="products" />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import NavLinks from '~/components/NavLinks.vue'
import ProductCards from '~/components/ProductCards.vue'

const products = ref([])

onMounted(async () => {
  const res = await fetch('https://dummyjson.com/products?limit=5')
  const data = await res.json()
  products.value = data.products
})
</script>