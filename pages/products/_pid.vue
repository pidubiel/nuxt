<template>
  <div>
    <h1>Single product</h1>
    <nuxt-link to="/products">Back to products</nuxt-link>
    <div v-if="productData.translated">
      <h1>{{ productData.name }}</h1>
      <h2>Stock: {{ productData.stock }}</h2>
      <h6>Product ID: {{ $route.params.pid }}</h6>
      <img v-bind:src="productData.cover.media.url" alt="Product image" style="max-height: 200px;" />
      <h6>Product Description: {{ productData.translated.description }}</h6>
      <h2 class="mt-5">Properties: {{ productData.sortedProperties }}</h2>
      <table class="table table-sm mt-5 col-lg-6">
        <tbody>
          <tr>
            <td>
              <strong>color</strong>
            </td>
            <td>@mdo</td>
          </tr>
          <tr>
            <td>
              <strong>content</strong>
            </td>
            <td>@fat</td>
          </tr>
          <tr>
            <td>
              <strong>length</strong>
            </td>
            <td>@twitter</td>
          </tr>
          <tr>
            <td>
              <strong>size</strong>
            </td>
            <td>@twitter</td>
          </tr>
          <tr>
            <td>
              <strong>textile</strong>
            </td>
            <td>@twitter</td>
          </tr>
          <tr>
            <td>
              <strong>width</strong>
            </td>
            <td>@twitter</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  layout: "products",
  async asyncData({ params }) {
    const config = {
      headers: {
        "sw-access-key": "SWSCZNJ1SKHBEXLUMWM1VMVPSG"
      }
    };
    const {
      data: { data }
    } = await axios.get(
      `http://192.168.33.10/sales-channel-api/v1/product/${params.pid}`,
      config
    );
    return { productData: data };
  }
};
</script>