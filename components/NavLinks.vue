<template>
  <div class="nav-container">
    <NuxtLink to="/">Go Home</NuxtLink>
    <a href="#" @click="$router.back()">
      Go Back
    </a>
  </div>
</template>

<script>
</script>

<style scoped>
.nav-container {
  margin-bottom: 16px;
}
.nav-container a {
  padding: 8px;
  border-radius: 8px;
  text-decoration: none;
  margin-right: 8px;
  color: black;
  transition: all 0.3s ease-in-out;
}
.nav-container a:hover {
  color: white;
  background: black;
}
</style>