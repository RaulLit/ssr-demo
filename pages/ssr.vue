<template>
  <div class="container">
    <h1>SSR Products</h1>
    <NavLinks />
    <p><strong>Notice</strong> when you click the card, how the Product details (green background) is already rendered when the page loads while the Review cards (red background) takes time to render</p>

    <ProductCards :products="data.products" />
  </div>
</template>

<script setup>
import NavLinks from '~/components/NavLinks.vue';
import ProductCards from '~/components/ProductCards.vue'

const { data } = await useFetch('https://dummyjson.com/products?limit=5')
</script>