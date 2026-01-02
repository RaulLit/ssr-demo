<template>
  <div class="container">
    <h1>CSR Products</h1>
    <NuxtLink to="/ssr">Go To SSR</NuxtLink>
    <NuxtLink to="/">Go Home</NuxtLink>

    <ProductCards v-if="products" :products="products" />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import ProductCards from '~/components/ProductCards.vue'

const products = ref([])

onMounted(async () => {
  const res = await fetch('https://dummyjson.com/products?limit=5')
  const data = await res.json()
  products.value = data.products
})
</script>