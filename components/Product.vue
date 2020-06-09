<template>
  <li class="product">
    <h1>{{ productName }}</h1>
  </li>
</template>

<script>
export default {
  name: "Product",
  props: ["productName", "productId"]
};
</script>

<style scoped>
.product {
  margin: 15px 0;
}
</style>
