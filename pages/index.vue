<template>
  <div class="container">
    <h1>Hello Developers!!</h1>
    <p>
      This project show cases the difference between Client Side Rendering (CSR)
      and Server Side Rendering. 
    </p>

    <div class="box-container">
      <div class="box csr">
        <p><strong>Notice</strong> how the product cards take split second time to load.</p>
        <NuxtLink to="/csr">Client Side Rendering (CSR)</NuxtLink>
      </div>
      <div class="box ssr">
        <p><strong>Notice</strong> how the product cards are already rendered when page loads.</p>
        <NuxtLink to="/ssr">Server Side Rendering (SSR)</NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>

</script>

<style>
  .container {
    width: 80%;
    margin: 0 auto;
  }
  .box-container {
    display: flex;
    gap: 24px;
  }
  .box {
    padding: 24px;
    width: 400px;
    height: 200px;
    display: flex;
    justify-content: center;
    align-items: start;
    flex-direction: column;
    border-radius: 16px;
  }
  .box p {
    font-size: 1.5rem;
  }
  .csr {
    background: #fcbabab9;
  }
  .ssr {
    background: #c2ffc2c9;
  }
</style>