<template>
  <div>
    <h1>Products</h1>
    <nuxt-link to="/">Home page</nuxt-link>
    <nuxt-link to="/products/1">Product 1</nuxt-link>
    <nuxt-link to="/products/2">Product 2</nuxt-link>
  </div>
</template>

<script>
export default {
  layout: "products"
};
</script>