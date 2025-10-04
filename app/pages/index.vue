<template>
    <div>
        <main class="main">
          <!-- Hero Section with Slider -->
          <section id="hero" class="hero">
            <div class="container" data-aos="fade-up" data-aos-delay="100">
              <Swiper
                :modules="modules"
                :slides-per-view="1"
                :loop="true"
                :autoplay="{ delay: 3000, disableOnInteraction: false }"
                :pagination="{ clickable: true }"
                :navigation="false"
                class="hero-swiper rounded-3"
              >
                <SwiperSlide v-for="(offer, index) in offers" :key="index">
                  <NuxtLink :to="{ path: '/products', query: { offerId: offer.id } }">
                    <div class="border rounded-3 shadow-lg w-100 w-md-75 mb-4 mx-auto bg-transparent" style="background: transparent !important; box-shadow: none;">
                      <div class="row align-items-center g-0">
                        <div class="col-12">
                          <img
                            :src="offer.image"
                            :alt="offer.title"
                            class="rounded w-100 object-fit-cover slider-image"
                          />
                        </div>
                      </div>
                    </div>
                  </NuxtLink>
                </SwiperSlide>
              </Swiper>
            </div>
          </section>

          <!-- categories -->
          <section id="themes-characters" class="section py-5">
            <div class="container text-center mb-5" data-aos="fade-up">
              <h2 class="fw-bold">Categories</h2>
            </div>

            <div class="container" data-aos="fade-up" data-aos-delay="100">
              <Swiper
                :modules="modules"
                :slides-per-view="2"
                :loop="true"
                :autoplay="{ delay: 3000, disableOnInteraction: false }"
                :breakpoints="{
                  0: { slidesPerView: 3, spaceBetween: 5 },
                  576: { slidesPerView: 3 },
                  768: { slidesPerView: 4 },
                  992: { slidesPerView: 5 },
                  1200: { slidesPerView: 6 }
                }"
                :navigation="false"
                class="category-swiper"
              >
                <!-- Character 1 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'spiderman' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/spiderman.jpg"
                        alt="Spider-Man"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Spider-Man</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 2 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'frozen' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/frozen.jpeg"
                        alt="Frozen"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Frozen</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 3 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'donald-duck' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/donald-duck.png"
                        alt="Donald Duck"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Donald Duck</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 4 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'avengers' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/avengers.jpeg"
                        alt="Avengers"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Avengers</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 5 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'barbie' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/barbie.png"
                        alt="Barbie"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Barbie</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 6 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'super-mario' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/super-mario.png"
                        alt="Super Mario"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Super Mario</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 1 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'spiderman' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/spiderman.jpg"
                        alt="Spider-Man"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Spider-Man</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 2 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'frozen' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/frozen.jpeg"
                        alt="Frozen"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Frozen</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 3 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'donald-duck' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/donald-duck.png"
                        alt="Donald Duck"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Donald Duck</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 4 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'avengers' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/avengers.jpeg"
                        alt="Avengers"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Avengers</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 5 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'barbie' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/barbie.png"
                        alt="Barbie"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Barbie</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>

                <!-- Character 6 -->
                <SwiperSlide>
                  <NuxtLink
                    :to="{ path: '/products', query: { characterId: 'super-mario' } }"
                    class="text-decoration-none"
                  >
                    <div
                      class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center"
                    >
                      <img
                        src="/assets/img/super-mario.png"
                        alt="Super Mario"
                        class="img-fluid rounded-5 mb-2 theme-img"
                      />
                      <h6 class="mt-2 fw-semibold text-dark">Super Mario</h6>
                    </div>
                  </NuxtLink>
                </SwiperSlide>
              </Swiper>
            </div>
          </section>

          <!-- New Arrival Section -->
          <section id="new-arrival" class="bestsellers-section section py-5">
            <div class="container text-center mb-5" data-aos="fade-up">
              <h2 class="fw-bold">New Arrival</h2>
            </div>

            <div class="container">
              <div class="row g-4">
                <div
                  v-for="product in newArrivals"
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

                    <h5 class="fw-semibold text-dark mb-1">{{ product.name }}</h5>
                    <p class="text-muted small mb-2">{{ product.description }}</p>

                    <!-- Pricing -->
                    <div class="mb-3">
                      <span class="text-muted text-decoration-line-through me-2">₹{{ product.originalPrice }}</span>
                      <span class="text-success fw-bold">₹{{ product.sellingPrice }}</span>
                    </div>

                    <!-- Actions: stacked on mobile -->
                    <div class="d-flex flex-column flex-md-row gap-2">
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
          </section>

            <!-- Best Sellers Section -->
            <section id="best-sellers" class="bestsellers-section section py-5">
              <div class="container text-center mb-5" data-aos="fade-up">
                <h2 class="fw-bold">Best Sellers</h2>
              </div>

              <div class="container">
                <div class="row g-4">
                  <div
                    v-for="product in bestSellers"
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

                      <h5 class="fw-semibold text-dark mb-1">{{ product.name }}</h5>
                      <p class="text-muted small mb-2">{{ product.description }}</p>

                      <!-- Pricing -->
                      <div class="mb-3">
                        <span class="text-muted text-decoration-line-through me-2">₹{{ product.originalPrice }}</span>
                        <span class="text-success fw-bold">₹{{ product.sellingPrice }}</span>
                      </div>

                      <!-- Actions: stacked on mobile -->
                      <div class="d-flex flex-column flex-md-row gap-2">
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
            </section>

        </main>
    </div>
</template>

<script setup>
  import { Swiper, SwiperSlide } from "swiper/vue";
  import { Navigation, Pagination, Autoplay } from "swiper/modules"; // ✅ Vue 3/Nuxt 3 correct import

  // Swiper styles
  import "swiper/css";
  import "swiper/css/navigation";
  import "swiper/css/pagination";

  // Offers data (example)
  const offers = [
    { id: 1, title: "Offer 1", image: "/assets/img/offer.jpeg" },
    { id: 2, title: "Offer 2", image: "/assets/img/offer2.jpeg" },
    { id: 3, title: "Offer 3", image: "/assets/img/offer.jpeg" },
  ];

  // Register Swiper modules
  const modules = [Navigation, Pagination, Autoplay];

  const newArrivals = [
    {
      id: 1,
      name: "Wooden Train Set",
      description: "Classic toy for kids",
      originalPrice: 3999,
      sellingPrice: 2499,
      image: "/assets/img/offer.jpeg",
    },
    {
      id: 2,
      name: "Remote Control Car",
      description: "High-speed racing RC",
      originalPrice: 4999,
      sellingPrice: 2999,
      image: "/assets/img/offer.jpeg",
    },
    {
      id: 3,
      name: "Puzzle Blocks",
      description: "Educational toy",
      originalPrice: 2499,
      sellingPrice: 1499,
      image: "/assets/img/offer.jpeg",
    },
    {
      id: 4,
      name: "Doll House",
      description: "Beautiful with furniture",
      originalPrice: 1999,
      sellingPrice: 999,
      image: "/assets/img/offer.jpeg",
    },
  ];

  const bestSellers = [
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

<style scoped>
.category-swiper {
  padding: 0 1rem;
}

.category-swiper .swiper-button-next,
.category-swiper .swiper-button-prev {
  color: #333;
  top: 40%;
}

.theme-card {
  width: 100%;
  max-width: 170px;
  margin: 0 auto;
}

.theme-img {
  height: 100px;
  width: 100px;
  object-fit: cover;
}

@media (max-width: 575.98px) {
  .theme-card {
    max-width: 90px !important;
    padding: 0.5rem !important;
  }

  .theme-img {
    width: 60px !important;
    height: 60px !important;
  }

  .theme-card h6 {
    font-size: 0.7rem !important;
  }
}
</style>
