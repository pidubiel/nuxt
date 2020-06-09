<template>
  <div>
    <h1>Products</h1>
    <nuxt-link to="/">Home page</nuxt-link>
    <nuxt-link to="/products/1">Product 1</nuxt-link>
    <nuxt-link to="/products/2">Product 2</nuxt-link>
    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 mt-5">
      <div v-for="item in products" :key="item.id" class="col mb-4">
        <div class="card">
          <img
            v-bind:src="item.cover.media.thumbnails[0].url"
            class="card-img-top"
            style="max-height: 150px;"
            alt="..."
          />
          <div class="card-body text-center">
            <h5 class="card-title text-left" style="min-height: 80px;">
              <router-link :to="`/products/${item.id}`">{{ item.translated.name }}</router-link>
            </h5>
            <p
              class="card-text text-left"
              style="font-size: 12px; min-height: 110px;"
            >{{ item.translated.description }}</p>
            <h3 class="text-center">
              <strong>{{ item.price[0].gross }}$</strong>
            </h3>
            <button class="btn btn-primary" @click="addToCart(item.id)">Add to shopping cart</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Product from "../../components/Product";

export default {
  components: {
    Product
  },
  layout: "products",
  async asyncData({ params }) {
    const config = {
      headers: {
        "sw-access-key": "SWSCZNJ1SKHBEXLUMWM1VMVPSG"
      }
    };
    const {
      data: { data }
    } = await axios.get(`${process.env.baseUrl}/product`, config);
    console.log("AsyncData");
    return { products: data };
  }
};
</script>

<style scoped>
.product-list {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>
