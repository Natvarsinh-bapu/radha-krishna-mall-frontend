<template>
  <div>
    <main class="main">
      <!-- Product Listing Section -->
      <section id="product-listing" class="section py-5 mt-5">
        <div class="container">
          <div class="row">
            <!-- Sidebar Filter -->
            <aside class="col-lg-3 col-md-4 mb-4 d-none d-md-block">
              <!-- Always visible on desktop -->
              <FilterSidebar />
            </aside>

            <!-- Product Grid -->
            <div class="col-lg-9 col-md-8">
              <!-- Mobile Filter Toggle -->
              <div class="d-flex justify-content-between align-items-center mb-4">
                <h5 class="fw-bold">products Collection</h5>
                <div class="d-md-none">
                  <button
                    class="btn btn-outline-primary btn-sm rounded-pill"
                    type="button"
                    data-bs-toggle="offcanvas"
                    data-bs-target="#filterSidebar"
                  >
                    Filters
                  </button>
                </div>
                <select class="form-select w-auto d-none d-md-block">
                  <option>Sort by: Default</option>
                  <option>Price: Low to High</option>
                  <option>Price: High to Low</option>
                  <option>Newest</option>
                </select>
              </div>

              <!-- Product Grid -->
              <div class="row g-4">
                <div
                  v-for="product in products"
                  :key="product.id"
                  class="col-6 col-sm-6 col-md-4"
                >
                  <div
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark product-card"
                  >
                    <!-- Image -->
                    <NuxtLink :to="`/products/${product.id}`">
                      <img
                        :src="product.image"
                        class="card-img-top rounded-top-4"
                        :alt="product.name"
                        style="height: 220px; object-fit: cover;"
                      />
                    </NuxtLink>

                    <!-- Body -->
                    <div class="card-body text-start">
                      <h6 class="fw-semibold">{{ product.name }}</h6>
                      <p class="text-muted small">{{ product.description }}</p>

                      <!-- Pricing -->
                      <p class="mb-2">
                        <span class="text-muted text-decoration-line-through me-2">
                          ₹{{ product.originalPrice }}
                        </span>
                        <span class="fw-bold text-dark">₹{{ product.sellingPrice }}</span>
                      </p>

                      <!-- Actions -->
                      <div class="d-flex gap-2">
                        <button class="btn btn-outline-primary btn-sm rounded-pill flex-grow-1">
                          Add to Cart
                        </button>
                        <button class="btn btn-danger btn-sm rounded-pill flex-grow-1">
                          Buy Now
                        </button>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Mobile Offcanvas Filter -->
      <div
        class="offcanvas offcanvas-start"
        tabindex="-1"
        id="filterSidebar"
      >
        <div class="offcanvas-header">
          <h5 class="offcanvas-title">Filters</h5>
          <button
            type="button"
            class="btn-close text-reset"
            data-bs-dismiss="offcanvas"
          ></button>
        </div>
        <div class="offcanvas-body">
          <FilterSidebar />
        </div>
      </div>
    </main>
  </div>
</template>

<script setup>
import FilterSidebar from "@/components/FilterSidebar.vue";

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
  ];
</script>
