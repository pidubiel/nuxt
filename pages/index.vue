<template>
  <div class="container">
    <Header />
  </div>
</template>

<script>
import Header from "~/components/Header.vue";
import axios from "axios";

export default {
  components: {
    Header
  },
  methods: {
    data() {
      return {
        contextToken: ""
      };
    },
    async getContextToken() {
      const config = {
        "sw-access-key": "SWSCZNJ1SKHBEXLUMWM1VMVPSG"
      };
      try {
        const token = await axios.post(
          `${process.env.baseUrl}/checkout/cart`,
          null,
          {
            headers: {
              "sw-access-key": "SWSCZNJ1SKHBEXLUMWM1VMVPSG"
            }
          }
        );
        this.contextToken = token.data["sw-context-token"];
        console.log("Token", this.contextToken);
      } catch (err) {
        console.log(err);
      }
    }
  },
  created() {
    console.log("CT!: ", this.contextToken);
    if (this.contextToken !== "") {
      this.getContextToken();
    }
  }
};
</script>

<style>
</style>
