<template>
  <div>
    <main class="main py-5">
      <!-- Page Header -->
      <section class="section text-center">
        <div class="container">
          <h2 class="fw-bold">My Wishlist</h2>
          <p class="text-muted">Save your favorite products and shop them later</p>
        </div>
      </section>

      <!-- Wishlist Items -->
      <section class="section">
        <div class="container">
          <div class="row g-4">
            <div
              v-for="i in 6"
              :key="i"
              class="col-6 col-sm-6 col-md-4 col-lg-3"
            >
              <div class="card wishlist-card border-0 shadow-sm rounded-4 h-100">
                <!-- Product Image -->
                <img
                  src="/assets/img/offer.jpeg"
                  :alt="`Wishlist Product ${i}`"
                  class="card-img-top rounded-top-4"
                  style="height: 200px; object-fit: cover;"
                />

                <!-- Product Body -->
                <div class="card-body text-center">
                  <h6 class="fw-semibold text-dark mb-1">Wishlist Product {{ i }}</h6>
                  <div class="mb-2">
                    <span class="text-muted text-decoration-line-through me-2">₹2,499</span>
                    <span class="text-success fw-bold">₹1,499</span>
                  </div>

                  <!-- Buttons -->
                  <div class="d-flex justify-content-center gap-2">
                    <button class="btn btn-sm btn-outline-danger rounded-pill">
                      <i class="bi bi-trash"></i>
                    </button>
                    <button class="btn btn-sm btn-primary rounded-pill">
                      <i class="bi bi-cart me-1"></i> Add to Cart
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Empty Wishlist Message -->
          <div v-if="wishlist.length === 0" class="text-center mt-5">
            <h5 class="text-muted">Your wishlist is empty</h5>
            <NuxtLink to="/shop" class="btn btn-danger mt-3 rounded-pill px-4 py-2">
              Start Shopping
            </NuxtLink>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref } from "vue";

// sample wishlist items (you can replace with Vuex/Pinia state later)
const wishlist = ref([1, 2, 3, 4, 5, 6]);
</script>
