<template>
  <div>
    <nuxt-link to="/">Back to home</nuxt-link>
    <h1>Checkout page</h1>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "Checkout",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Shopware API app"
        }
      ]
    };
  }
};
</script>