<template>
  <div class="container">
    <h1>SSR Products</h1>
    <NuxtLink to="/csr">Go To CSR</NuxtLink>
    <NuxtLink to="/">Go Home</NuxtLink>

    <ProductCards :products="data.products" />
  </div>
</template>

<script setup>
import ProductCards from '~/components/ProductCards.vue'

const { data } = await useFetch('https://dummyjson.com/products?limit=5')
</script>