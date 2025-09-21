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
              v-for="product in wishlist"
              :key="product.id"
              class="col-6 col-sm-6 col-md-4 col-lg-3"
            >
              <div class="card wishlist-card border-0 shadow-sm rounded-4 h-100 text-start">
                <!-- Product Image -->
                <img
                  :src="product.image"
                  :alt="product.name"
                  class="card-img-top rounded-top-4"
                  style="height: 200px; object-fit: cover;"
                />

                <!-- Product Body -->
                <div class="card-body">
                  <h6 class="fw-semibold text-dark mb-1">{{ product.name }}</h6>
                  <p class="text-muted small mb-2">{{ product.description }}</p>

                  <!-- Pricing -->
                  <div class="mb-3">
                    <span class="text-muted text-decoration-line-through me-2">₹{{ product.originalPrice }}</span>
                    <span class="text-success fw-bold">₹{{ product.sellingPrice }}</span>
                  </div>

                  <!-- Buttons -->
                  <div class="d-flex gap-2">
                    <button
                      class="btn btn-sm btn-outline-danger rounded-pill"
                      @click="removeFromWishlist(product.id)"
                    >
                      <i class="bi bi-trash"></i>
                    </button>
                    <button
                      class="btn btn-sm btn-primary rounded-pill flex-grow-1"
                      @click="addToCart(product)"
                    >
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

const wishlist = ref([
  {
    id: 1,
    name: "Wishlist Product 1",
    description: "Special edition toy",
    originalPrice: 2499,
    sellingPrice: 1499,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 2,
    name: "Wishlist Product 2",
    description: "Fun & educational",
    originalPrice: 1999,
    sellingPrice: 1299,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 3,
    name: "Wishlist Product 3",
    description: "Popular choice",
    originalPrice: 1599,
    sellingPrice: 999,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 4,
    name: "Wishlist Product 4",
    description: "Best seller",
    originalPrice: 2999,
    sellingPrice: 2199,
    image: "/assets/img/offer.jpeg",
  },
]);

// actions
const removeFromWishlist = (id) => {
  wishlist.value = wishlist.value.filter((item) => item.id !== id);
};

const addToCart = (product) => {
  console.log("Add to cart:", product);
  // here you could dispatch to Pinia/Vuex cart store
};
</script>
