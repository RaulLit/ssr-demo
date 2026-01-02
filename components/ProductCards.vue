<template>
  <div class="card-container">
    <div v-for="p in products" :key="p.id" @click="() => router.push(`/product/${p.id}`)" class="card">
      <h3>{{ p.title }}</h3>
      <p>{{ p.description }}</p>
      <strong>₹{{ p.price }}</strong>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  products: Object,
})
const router = useRouter()
</script>

<style scoped>
.card-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 24px;

}
.card {
  padding: 24px;
  border-radius: 8px;
  border: 1px solid lightgray;
  background: #ddd;
}
.card:hover {
  box-shadow: 1px 2px 10px gray;
  cursor: pointer;
}
</style>