<template>
  <div>
    <h1>Single product</h1>
    <p>Product ID: {{ $route.params.pid }}</p>
  </div>
</template>

<script>
export default {
  layout: "products"
};
</script>