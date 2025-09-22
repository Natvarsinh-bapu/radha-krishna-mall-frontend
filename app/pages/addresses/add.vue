<template>
  <div>
    <main class="main py-5">
      <!-- Page Header -->
      <section class="section text-center mb-4">
        <div class="container">
          <h2 class="fw-bold">Add New Address</h2>
          <p class="text-muted">Save your shipping or billing address</p>
        </div>
      </section>

      <!-- Address Form -->
      <section class="section">
        <div class="container">
          <div class="card border-0 shadow-sm rounded-4 p-4 mx-auto" style="max-width: 600px;">
            <form @submit.prevent="saveAddress">
              <!-- Name -->
              <div class="mb-3">
                <label class="form-label fw-semibold">Full Name</label>
                <input
                  type="text"
                  v-model="form.name"
                  class="form-control rounded-3"
                  placeholder="Enter full name"
                  required
                />
              </div>

              <!-- Mobile -->
              <div class="mb-3">
                <label class="form-label fw-semibold">Mobile Number</label>
                <input
                  type="tel"
                  v-model="form.mobile"
                  class="form-control rounded-3"
                  placeholder="+91 XXXXX XXXXX"
                  required
                />
              </div>

              <!-- Street -->
              <div class="mb-3">
                <label class="form-label fw-semibold">Street Address</label>
                <textarea
                  v-model="form.street"
                  class="form-control rounded-3"
                  rows="2"
                  placeholder="Flat / House No., Area, Landmark"
                  required
                ></textarea>
              </div>

              <!-- City & State -->
              <div class="row">
                <div class="col-md-6 mb-3">
                  <label class="form-label fw-semibold">City</label>
                  <input
                    type="text"
                    v-model="form.city"
                    class="form-control rounded-3"
                    placeholder="Enter city"
                    required
                  />
                </div>
                <div class="col-md-6 mb-3">
                  <label class="form-label fw-semibold">State</label>
                  <input
                    type="text"
                    v-model="form.state"
                    class="form-control rounded-3"
                    placeholder="Enter state"
                    required
                  />
                </div>
              </div>

              <!-- Pincode -->
              <div class="mb-3">
                <label class="form-label fw-semibold">Pincode</label>
                <input
                  type="text"
                  v-model="form.pincode"
                  class="form-control rounded-3"
                  placeholder="Enter pincode"
                  required
                />
              </div>

              <!-- Default Checkbox -->
              <div class="form-check mb-3">
                <input
                  class="form-check-input"
                  type="checkbox"
                  v-model="form.isDefault"
                  id="defaultAddress"
                />
                <label class="form-check-label" for="defaultAddress">
                  Set as default address
                </label>
              </div>

              <!-- Buttons -->
              <div class="d-flex justify-content-between">
                <NuxtLink to="/addresses" class="btn btn-outline-secondary rounded-pill px-4">
                  Cancel
                </NuxtLink>
                <button type="submit" class="btn btn-primary rounded-pill px-4">
                  Save Address
                </button>
              </div>
            </form>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const form = reactive({
  name: "",
  mobile: "",
  street: "",
  city: "",
  state: "",
  pincode: "",
  isDefault: false,
});

const saveAddress = () => {
  console.log("Saved Address:", form);
  alert("Address saved successfully!");
  // redirect to address list page
};
</script>
