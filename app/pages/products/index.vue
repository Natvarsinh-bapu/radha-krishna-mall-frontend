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
                <div class="col-6 col-sm-6 col-md-4">
                  <NuxtLink
                    to="/products/1"
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark"
                  >
                    <img
                      src="/assets/img/offer.jpeg"
                      class="card-img-top rounded-top-4"
                      alt="Toy 1"
                      style="height: 220px; object-fit: cover;"
                    />
                    <div class="card-body text-center">
                      <h6 class="fw-semibold">LEGO City Police Set</h6>
                      <p class="text-muted small">Ages 6+</p>
                      <p class="fw-bold text-dark">₹1,299</p>
                      <button class="btn btn-primary btn-sm rounded-pill">
                        View Details
                      </button>
                    </div>
                  </NuxtLink>
                </div>

                <div class="col-6 col-sm-6 col-md-4">
                  <NuxtLink
                    to="/products/1"
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark"
                  >
                    <img
                      src="/assets/img/offer.jpeg"
                      class="card-img-top rounded-top-4"
                      alt="Toy 1"
                      style="height: 220px; object-fit: cover;"
                    />
                    <div class="card-body text-center">
                      <h6 class="fw-semibold">LEGO City Police Set</h6>
                      <p class="text-muted small">Ages 6+</p>
                      <p class="fw-bold text-dark">₹1,299</p>
                      <button class="btn btn-primary btn-sm rounded-pill">
                        View Details
                      </button>
                    </div>
                  </NuxtLink>
                </div>

                <div class="col-6 col-sm-6 col-md-4">
                  <NuxtLink
                    to="/products/1"
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark"
                  >
                    <img
                      src="/assets/img/offer.jpeg"
                      class="card-img-top rounded-top-4"
                      alt="Toy 1"
                      style="height: 220px; object-fit: cover;"
                    />
                    <div class="card-body text-center">
                      <h6 class="fw-semibold">LEGO City Police Set</h6>
                      <p class="text-muted small">Ages 6+</p>
                      <p class="fw-bold text-dark">₹1,299</p>
                      <button class="btn btn-primary btn-sm rounded-pill">
                        View Details
                      </button>
                    </div>
                  </NuxtLink>
                </div>

                <div class="col-6 col-sm-6 col-md-4">
                  <NuxtLink
                    to="/products/1"
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark"
                  >
                    <img
                      src="/assets/img/offer.jpeg"
                      class="card-img-top rounded-top-4"
                      alt="Toy 1"
                      style="height: 220px; object-fit: cover;"
                    />
                    <div class="card-body text-center">
                      <h6 class="fw-semibold">LEGO City Police Set</h6>
                      <p class="text-muted small">Ages 6+</p>
                      <p class="fw-bold text-dark">₹1,299</p>
                      <button class="btn btn-primary btn-sm rounded-pill">
                        View Details
                      </button>
                    </div>
                  </NuxtLink>
                </div>

                <div class="col-6 col-sm-6 col-md-4">
                  <NuxtLink
                    to="/products/1"
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark"
                  >
                    <img
                      src="/assets/img/offer.jpeg"
                      class="card-img-top rounded-top-4"
                      alt="Toy 1"
                      style="height: 220px; object-fit: cover;"
                    />
                    <div class="card-body text-center">
                      <h6 class="fw-semibold">LEGO City Police Set</h6>
                      <p class="text-muted small">Ages 6+</p>
                      <p class="fw-bold text-dark">₹1,299</p>
                      <button class="btn btn-primary btn-sm rounded-pill">
                        View Details
                      </button>
                    </div>
                  </NuxtLink>
                </div>

                <div class="col-6 col-sm-6 col-md-4">
                  <NuxtLink
                    to="/products/1"
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark"
                  >
                    <img
                      src="/assets/img/offer.jpeg"
                      class="card-img-top rounded-top-4"
                      alt="Toy 1"
                      style="height: 220px; object-fit: cover;"
                    />
                    <div class="card-body text-center">
                      <h6 class="fw-semibold">LEGO City Police Set</h6>
                      <p class="text-muted small">Ages 6+</p>
                      <p class="fw-bold text-dark">₹1,299</p>
                      <button class="btn btn-primary btn-sm rounded-pill">
                        View Details
                      </button>
                    </div>
                  </NuxtLink>
                </div>

                <div class="col-6 col-sm-6 col-md-4">
                  <NuxtLink
                    to="/products/1"
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark"
                  >
                    <img
                      src="/assets/img/offer.jpeg"
                      class="card-img-top rounded-top-4"
                      alt="Toy 1"
                      style="height: 220px; object-fit: cover;"
                    />
                    <div class="card-body text-center">
                      <h6 class="fw-semibold">LEGO City Police Set</h6>
                      <p class="text-muted small">Ages 6+</p>
                      <p class="fw-bold text-dark">₹1,299</p>
                      <button class="btn btn-primary btn-sm rounded-pill">
                        View Details
                      </button>
                    </div>
                  </NuxtLink>
                </div>

                <div class="col-6 col-sm-6 col-md-4">
                  <NuxtLink
                    to="/products/1"
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark"
                  >
                    <img
                      src="/assets/img/offer.jpeg"
                      class="card-img-top rounded-top-4"
                      alt="Toy 1"
                      style="height: 220px; object-fit: cover;"
                    />
                    <div class="card-body text-center">
                      <h6 class="fw-semibold">LEGO City Police Set</h6>
                      <p class="text-muted small">Ages 6+</p>
                      <p class="fw-bold text-dark">₹1,299</p>
                      <button class="btn btn-primary btn-sm rounded-pill">
                        View Details
                      </button>
                    </div>
                  </NuxtLink>
                </div>

                <div class="col-6 col-sm-6 col-md-4">
                  <NuxtLink
                    to="/products/1"
                    class="card h-100 shadow-sm border rounded-4 text-decoration-none text-dark"
                  >
                    <img
                      src="/assets/img/offer.jpeg"
                      class="card-img-top rounded-top-4"
                      alt="Toy 1"
                      style="height: 220px; object-fit: cover;"
                    />
                    <div class="card-body text-center">
                      <h6 class="fw-semibold">LEGO City Police Set</h6>
                      <p class="text-muted small">Ages 6+</p>
                      <p class="fw-bold text-dark">₹1,299</p>
                      <button class="btn btn-primary btn-sm rounded-pill">
                        View Details
                      </button>
                    </div>
                  </NuxtLink>
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
</script>
