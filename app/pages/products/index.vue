<template>
  <div>
    <main class="main">
      <!-- Product Listing Section -->
      <section id="product-listing" class="section py-5 mt-5">
        <div class="container">
          <div class="row">
            <!-- Overlay (for mobile) -->
            <transition name="fade">
              <div
                v-if="showFilter"
                class="mobile-overlay d-md-none"
                @click="toggleFilter"
              ></div>
            </transition>

            <!-- Filter Sidebar -->
            <transition name="slide-fade">
              <aside
                v-if="showFilter"
                class="col-lg-3 col-md-4 mb-4 border-end pe-3 filter-sidebar"
              >
                <!-- Mobile Close Button -->
                <div
                  class="d-flex justify-content-between align-items-center mb-3 d-md-none sidebar-header"
                >
                  <h5 class="fw-bold mb-0">Filters</h5>
                  <button
                    class="filter-btn btn btn-outline-secondary btn-sm rounded-pill"
                    @click="toggleFilter"
                  >
                    <i class="bi bi-x-lg"></i>
                  </button>
                </div>

                <FilterSidebar />
              </aside>
            </transition>

            <!-- Product Grid -->
            <div :class="showFilter ? 'col-lg-9 col-md-8' : 'col-12'">
              <!-- Header Row -->
              <div class="d-flex justify-content-between align-items-center mb-4">
                <h5 class="fw-bold mb-0">Products Collection</h5>

                <!-- Filter Toggle Button (Mobile) -->
                <button
                  class="filter-btn btn btn-outline-primary btn-sm rounded-pill d-md-none"
                  @click="toggleFilter"
                >
                  {{ showFilter ? "Hide Filters" : "Filter" }}
                </button>

                <!-- Desktop Controls -->
                <div class="d-none d-md-flex align-items-center gap-2">
                  <button
                    class="btn btn-outline-primary btn-sm rounded-pill"
                    @click="toggleFilter"
                  >
                    {{ showFilter ? "Hide Filters" : "Filter" }}
                  </button>

                  <select class="form-select w-auto">
                    <option>Sort by: Default</option>
                    <option>Price: Low to High</option>
                    <option>Price: High to Low</option>
                    <option>Newest</option>
                  </select>
                </div>
              </div>

              <!-- Product Grid -->
              <div class="row g-4">
                <div
                  v-for="product in products"
                  :key="product.id"
                  :class="productColClass"
                >
                  <div
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark product-card"
                  >
                    <NuxtLink :to="`/products/${product.id}`">
                      <img
                        :src="product.image"
                        class="card-img-top rounded-top-4"
                        :alt="product.name"
                        style="height: 220px; object-fit: cover;"
                      />
                    </NuxtLink>

                    <div class="card-body text-start">
                      <h6 class="fw-semibold product-name">{{ product.name }}</h6>

                      <p class="mb-2">
                        <span
                          class="product-price text-muted text-decoration-line-through me-2"
                        >
                          ₹{{ product.originalPrice }}
                        </span>
                        <span class="product-price fw-bold text-dark">
                          ₹{{ product.sellingPrice }}
                        </span>
                      </p>

                      <div class="d-flex flex-column flex-md-row gap-2">
                        <button
                          class="btn-product-card btn btn-outline-primary btn-sm rounded-pill flex-grow-1"
                        >
                          Add to Cart
                        </button>
                        <button
                          class="btn-product-card btn btn-danger btn-sm rounded-pill flex-grow-1"
                        >
                          Buy Now
                        </button>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <!-- /Product Grid -->
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import FilterSidebar from "@/components/FilterSidebar.vue";

const showFilter = ref(false);

const toggleFilter = () => {
  showFilter.value = !showFilter.value;
};

const productColClass = computed(() =>
  showFilter.value
    ? "col-6 col-sm-6 col-md-4 col-lg-4"
    : "col-6 col-sm-6 col-md-3 col-lg-3"
);

const products = [
  {
    id: 1,
    name: "LEGO City Police Set",
    description: "Ages 6+",
    originalPrice: 1599,
    sellingPrice: 1299,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 2,
    name: "Hot Wheels Car Pack",
    description: "Pack of 5 racing cars",
    originalPrice: 899,
    sellingPrice: 699,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 3,
    name: "Barbie Dreamhouse",
    description: "Includes accessories",
    originalPrice: 5999,
    sellingPrice: 4999,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 4,
    name: "Puzzle Game Set",
    description: "Boosts problem-solving",
    originalPrice: 599,
    sellingPrice: 449,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 5,
    name: "Toy Robot",
    description: "Interactive and fun",
    originalPrice: 999,
    sellingPrice: 799,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 6,
    name: "Building Blocks",
    description: "Enhance creativity",
    originalPrice: 1299,
    sellingPrice: 999,
    image: "/assets/img/offer.jpeg",
  },
];
</script>

<style scoped>
/* Sidebar and overlay transitions */
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: transform 0.3s ease, opacity 0.3s ease;
}
.slide-fade-enter-from {
  transform: translateX(-100%);
  opacity: 0;
}
.slide-fade-leave-to {
  transform: translateX(-100%);
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Overlay for mobile sidebar */
.mobile-overlay {
  position: fixed;
  top: 93px; /* same as header height */
  left: 0;
  width: 100%;
  height: calc(100% - 60px);
  background: rgba(0, 0, 0, 0.4);
  z-index: 1049;
}

/* Mobile sidebar style */
@media (max-width: 767.98px) {
  .filter-sidebar {
    position: fixed;
    top: 93px; /* below header */
    left: 0;
    z-index: 1050;
    width: 100%; /* full width */
    height: calc(100% - 60px);
    background-color: #fff;
    overflow-y: auto;
    padding: 1rem;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  }

  .sidebar-header {
    position: sticky;
    top: 0;
    background: white;
    padding: 0 10px;
    z-index: 1051;
  }
}
</style>
