<template>
  <div>
    <main class="main py-5">
      <!-- Page Header -->
      <section class="section text-center mb-4">
        <div class="container">
          <h2 class="fw-bold">My Addresses</h2>
          <p class="text-muted">Manage your shipping and billing addresses</p>
          <NuxtLink
            to="/"
            class="btn btn-primary mt-3 rounded-pill px-4 py-2"
          >
            <i class="bi bi-plus-lg me-1"></i> Add New Address
          </NuxtLink>
        </div>
      </section>

      <!-- Addresses Section -->
      <section class="section">
        <div class="container">
          <div v-if="addresses.length > 0" class="row g-4">
            <div
              v-for="(address, index) in addresses"
              :key="index"
              class="col-md-6 col-lg-4"
            >
              <div class="card border-0 shadow-sm rounded-4 h-100">
                <div class="card-body">
                  <!-- Header -->
                  <div class="d-flex justify-content-between align-items-center mb-2">
                    <h6 class="fw-bold mb-0">{{ address.name }}</h6>
                    <span
                      v-if="address.isDefault"
                      class="badge bg-success rounded-pill"
                    >
                      Default
                    </span>
                  </div>

                  <!-- Details -->
                  <p class="mb-1 text-muted small">{{ address.mobile }}</p>
                  <p class="mb-1">{{ address.street }}</p>
                  <p class="mb-1">{{ address.city }}, {{ address.state }}</p>
                  <p class="mb-3">Pincode: {{ address.pincode }}</p>

                  <!-- Actions -->
                  <div class="d-flex justify-content-between mt-3">
                    <button
                      class="btn btn-sm btn-outline-primary rounded-pill"
                      @click="editAddress(index)"
                    >
                      <i class="bi bi-pencil-square me-1"></i> Edit
                    </button>
                    <button
                      class="btn btn-sm btn-outline-danger rounded-pill"
                      @click="deleteAddress(index)"
                    >
                      <i class="bi bi-trash me-1"></i> Delete
                    </button>
                    <button
                      v-if="!address.isDefault"
                      class="btn btn-sm btn-outline-success rounded-pill"
                      @click="setDefault(index)"
                    >
                      <i class="bi bi-check-circle me-1"></i> Set Default
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Empty State -->
          <div v-else class="text-center py-5">
            <h5 class="text-muted">No saved addresses</h5>
            <NuxtLink
              to="/addresses/add"
              class="btn btn-primary mt-3 rounded-pill px-4 py-2"
            >
              Add Address
            </NuxtLink>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref } from "vue";

const addresses = ref([
  {
    name: "John Doe",
    mobile: "+91 98765 43210",
    street: "123, Park Street",
    city: "Mumbai",
    state: "Maharashtra",
    pincode: "400001",
    isDefault: true,
  },
  {
    name: "Jane Smith",
    mobile: "+91 91234 56789",
    street: "45, Green Avenue",
    city: "Delhi",
    state: "Delhi",
    pincode: "110001",
    isDefault: false,
  },
]);

// Actions
const editAddress = (index) => {
  alert("Edit address: " + addresses.value[index].name);
};
const deleteAddress = (index) => {
  addresses.value.splice(index, 1);
};
const setDefault = (index) => {
  addresses.value.forEach((addr, i) => (addr.isDefault = i === index));
};
</script>
