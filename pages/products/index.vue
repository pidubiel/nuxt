<template>
  <div>
    <h1>Products</h1>
    <nuxt-link to="/">Home page</nuxt-link>
    <nuxt-link to="/products/1">Product 1</nuxt-link>
    <nuxt-link to="/products/2">Product 2</nuxt-link>
    <ul>
      <li v-for="product in products" :key="product.id">
        {{ product.name }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  layout: "products",
  data() {
    return {
      products: []
    };
  },
  async created() {
    const config = {
      headers: {
        "sw-access-key": "SWSCZNJ1SKHBEXLUMWM1VMVPSG"
      }
    };
    try {
      const res = await axios.get(
        "http://192.168.33.10/sales-channel-api/v1/product",
        config
      );
      this.products = res.data.data;
    } catch (err) {
      console.log(err);
    }
  }
};
</script>
