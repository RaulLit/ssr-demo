<template>
  <div class="container">
    <NavLinks />

    <div class="ssr">
      <h4>Server Side Rendered</h4>
      <h1>Product Details</h1>
      <h2>{{ product.title || "Title"}}</h2>
      <p>{{ product.description || "Description" }}</p>
      <h3>${{ product.price || "Price" }}</h3>
      <h5>Rating: {{ product.rating || "Rating" }}</h5>
    </div>

    <div class="csr">
      <h4>Client Side Rendered</h4>
      <h1>Reviews</h1>
      <div v-for="r,i in reviews" :key="i" class="card">
        <p>Rating: {{ r.rating }}</p>
        <p>Comment: <strong>{{ r.comment }}</strong></p>
        <p>Author: {{ r.reviewerName }}</p>
      </div>
    </div>

  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import NavLinks from '~/components/NavLinks.vue';
const route = useRoute();
const id = route.params.id;

const reviews = ref([])

const { data: product } = await useFetch(`https://dummyjson.com/products/${id}?select=title,description,price,rating`)

onMounted(async () => {
  const res = await fetch(`https://dummyjson.com/products/${id}?select=reviews`)
  const data = await res.json()
  reviews.value = data.reviews
})
</script>

<style scoped>
.container {
  margin-top: 24px;
}
.ssr, .csr {
  padding: 16px
}
.card {
  padding: 16px;
  border-radius: 8px;
  border: 1px solid lightgray;
  background: #fff;
  margin-bottom: 8px;
}
.card p {
  margin: 0;
}
</style>