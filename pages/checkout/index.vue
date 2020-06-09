<template>
  <div>
    <nuxt-link to="/">Back to home</nuxt-link>
    <div>
      <h1 class="mb-3">Checkout</h1>
      <hr />
      <div class="row">
        <div class="col-md-8 order-md-1">
          <h4 class="mb-3">Shipping information</h4>
          <form class="needs-validation" novalidate>
            <div class="row">
              <div class="col-md-5 mb-3">
                <label for="country">Salutation*</label>
                <select
                  class="custom-select d-block w-100"
                  id="country"
                  required
                  v-model="shippingInfo.salutation"
                >
                  <option value disabled="disabled">Enter Salutation...</option>
                  <option>Not specified</option>
                  <option>Mrs.</option>
                  <option>Mr.</option>
                </select>
                <div class="invalid-feedback">Please select a valid country.</div>
              </div>
            </div>

            <div class="row">
              <div class="col-md-6 mb-3">
                <label for="firstName">First name*</label>
                <input
                  type="text"
                  class="form-control"
                  v-model="shippingInfo.firstName"
                  id="firstName"
                  placeholder="Enter first name..."
                  value
                  required
                />
                <div class="invalid-feedback">Valid first name is required.</div>
              </div>
              <div class="col-md-6 mb-3">
                <label for="lastName">Last name*</label>
                <input
                  type="text"
                  class="form-control"
                  v-model="shippingInfo.lastName"
                  id="lastName"
                  placeholder="Enter last name..."
                  value
                  required
                />
                <div class="invalid-feedback">Valid last name is required.</div>
              </div>
            </div>

            <div class="mb-3">
              <label for="email">Email*</label>
              <input
                type="email"
                class="form-control"
                v-model="shippingInfo.email"
                id="email"
                placeholder="you@example.com"
              />
              <div class="invalid-feedback">Please enter a valid email address for shipping updates.</div>
            </div>

            <p class="mt-5">
              <strong>Your address</strong>
            </p>
            <hr />

            <div class="row">
              <div class="col-md-5 mb-3">
                <label for="zip">Street address*</label>
                <input
                  type="text"
                  class="form-control"
                  v-model="shippingInfo.street"
                  id="zip"
                  placeholder="Enter street address..."
                  required
                />
                <div class="invalid-feedback">Zip code required.</div>
              </div>
              <div class="col-md-3 mb-3">
                <label for="zip">Postal code*</label>
                <input
                  type="text"
                  class="form-control"
                  v-model="shippingInfo.zipCode"
                  id="zip"
                  placeholder="Enter postal code..."
                  required
                />
                <div class="invalid-feedback">Zip code required.</div>
              </div>
              <div class="col-md-4 mb-3">
                <label for="zip">City*</label>
                <input
                  type="text"
                  class="form-control"
                  v-model="shippingInfo.city"
                  id="zip"
                  placeholder="Enter city..."
                  required
                />
                <div class="invalid-feedback">Zip code required.</div>
              </div>
            </div>
            <div class="row">
              <div class="col-md-4 mb-3">
                <label for="address">Country*</label>
                <input
                  type="text"
                  class="form-control"
                  v-model="shippingInfo.country"
                  id="address"
                  placeholder="Enter country..."
                  required
                />
                <div class="invalid-feedback">Please enter your shipping address.</div>
              </div>
            </div>

            <hr class="mb-4" />
          </form>
          <button @click="getSalutation" class="btn btn-primary btn-lg btn-block">Get salutation</button>
          <button @click="getCountry" class="btn btn-primary btn-lg btn-block">Get country</button>
          <button @click="simpleOrder" class="btn btn-primary btn-lg btn-block">Simple order</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      shippingInfo: {
        salutation: "",
        firstName: "",
        lastName: "",
        email: "",
        street: "",
        zipCode: "",
        city: "",
        country: ""
      }
    };
  },
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