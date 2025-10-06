<template>
  <div>
    <main class="main">
      <!-- Product Details Section -->
      <section class="section py-5 mt-5">
        <div class="container">
          <div class="row g-5">
            <!-- Product Images -->
            <div class="col-lg-6">
              <div class="card shadow-sm border rounded-4 p-3">
                <img
                  src="/assets/img/offer.jpeg"
                  alt="Product Main"
                  class="img-fluid rounded-4 mb-3"
                  style="height: 380px; object-fit: cover;"
                />
                <div class="d-flex gap-3">
                  <img
                    src="/assets/img/offer.jpeg"
                    alt="Thumbnail 1"
                    class="img-thumbnail rounded-3"
                    style="width: 80px; height: 80px; object-fit: cover; cursor: pointer;"
                  />
                  <img
                    src="/assets/img/offer.jpeg"
                    alt="Thumbnail 2"
                    class="img-thumbnail rounded-3"
                    style="width: 80px; height: 80px; object-fit: cover; cursor: pointer;"
                  />
                  <img
                    src="/assets/img/offer.jpeg"
                    alt="Thumbnail 3"
                    class="img-thumbnail rounded-3"
                    style="width: 80px; height: 80px; object-fit: cover; cursor: pointer;"
                  />
                </div>
              </div>
            </div>

            <!-- Product Info -->
            <div class="col-lg-6">
              <h2 class="fw-bold mb-3">LEGO City Police Set</h2>
              <p class="text-success fw-semibold">In Stock</p>
              <h3 class="fw-bold text-primary mb-3">₹1,299</h3>

              <p class="mb-3">
                Build exciting adventures with this LEGO City Police Set. Includes multiple figures,
                vehicles, and accessories to inspire creativity and roleplay.
              </p>

              <!-- Specifications -->
              <ul class="list-unstyled mb-4">
                <li><strong>Brand:</strong> LEGO</li>
                <li><strong>Age Group:</strong> 6+ years</li>
                <li><strong>Material:</strong> ABS Plastic</li>
                <li><strong>Dimensions:</strong> 25 x 18 x 6 cm</li>
              </ul>

              <!-- Add to Cart & Buy Now Buttons -->
              <div class="d-flex flex-column flex-lg-row gap-3">
                <button class="btn-product-card btn btn-outline-primary rounded-pill flex-grow-1">
                  Add to Cart
                </button>
                <button class="btn-product-card btn btn-danger rounded-pill flex-grow-1">
                  Buy Now
                </button>
              </div>
            </div>
          </div>

          <!-- Related Products -->
          <div class="row mt-5">
            <div class="container text-center mb-5" data-aos="fade-up">
              <h2 class="fw-bold">Best Sellers</h2>
            </div>

            <div class="container">
              <div class="row g-4">
                <div
                  v-for="product in relatedProducts"
                  :key="product.id"
                  class="col-6 col-sm-6 col-md-3"
                >
                  <div class="product-card card border-0 shadow-sm rounded-4 p-3 h-100 text-start">
                    <NuxtLink :to="`/products/${product.id}`">
                      <img
                        :src="product.image"
                        :alt="product.name"
                        class="img-fluid rounded-3 mb-3"
                        style="height: 200px; object-fit: cover;"
                      />
                    </NuxtLink>

                    <h5 class="fw-semibold text-dark mb-1 product-name">{{ product.name }}</h5>
                    <p class="text-muted small mb-2 product-description">{{ product.description }}</p>

                    <!-- Pricing -->
                    <div class="mb-3">
                      <span class="product-price text-muted text-decoration-line-through me-2">₹{{ product.originalPrice }}</span>
                      <span class="product-price text-success fw-bold">₹{{ product.sellingPrice }}</span>
                    </div>

                    <!-- Actions: stacked on mobile -->
                    <div class="d-flex flex-column flex-md-row gap-2">
                      <button class="btn-product-card btn btn-outline-primary btn-sm rounded-pill flex-grow-1">
                        Add to Cart
                      </button>
                      <button class="btn-product-card btn btn-danger btn-sm rounded-pill flex-grow-1">
                        Buy Now
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
const relatedProducts = [
  {
    id: 5,
    name: "Action Figure Set",
    description: "Superhero collection",
    originalPrice: 3999,
    sellingPrice: 2499,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 6,
    name: "Drone Camera Toy",
    description: "Fun flying drone",
    originalPrice: 4999,
    sellingPrice: 2999,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 7,
    name: "Building Blocks",
    description: "Creative play set",
    originalPrice: 2499,
    sellingPrice: 1499,
    image: "/assets/img/offer.jpeg",
  },
  {
    id: 8,
    name: "RC Helicopter",
    description: "Lightweight & durable",
    originalPrice: 1999,
    sellingPrice: 999,
    image: "/assets/img/offer.jpeg",
  },
];
</script>
