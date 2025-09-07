<template>
    <div>
        <main class="main">
          <!-- hero section -->
          <section id="hero" class="hero section">
              <div class="container" data-aos="fade-up" data-aos-delay="100">
                <div>
                    <div class="hero-content" data-aos="fade-up" data-aos-delay="200">
                      <NuxtLink :to="{ path: '/products', query: { offerId: 1 } }">
                        <div class="border rounded-3 bg-white shadow-lg w-100 w-md-75 mb-4 mx-auto">
                          <div class="row align-items-center g-0">
                            <div class="col-5">
                              <img src="/assets/img/offer.jpeg" alt="Offer 1" height="100" class="rounded-start w-100 object-fit-cover" />
                            </div>
                            <div class="col-7">
                              <div class="p-2">
                                <h2 class="text-danger mb-1"><b>Offer</b></h2>
                                <h5 class="text-primary">Save Upto 40%</h5>
                              </div>
                            </div>
                          </div>
                        </div>
                      </NuxtLink>

                      <!-- Offer Card 2 -->
                      <NuxtLink :to="{ path: '/products', query: { offerId: 2 } }">
                        <div class="border rounded-3 bg-white shadow-lg w-100 w-md-75 mb-4 mx-auto">
                          <div class="row align-items-center g-0">
                            <div class="col-5">
                              <img src="/assets/img/offer2.jpeg" alt="Offer 2" height="100" class="rounded-start w-100 object-fit-cover" />
                            </div>
                            <div class="col-7">
                              <div class="p-2">
                                <h2 class="text-danger mb-1"><b>Offer</b></h2>
                                <h5 class="text-primary">Save Upto 50%</h5>
                              </div>
                            </div>
                          </div>
                        </div>
                      </NuxtLink>
                    </div>
                  </div>
              </div>
          </section>

          <!-- categories -->
          <section id="themes-characters" class="section py-5">
            <div class="container text-center mb-5" data-aos="fade-up">
              <h2 class="fw-bold">Categories</h2>
            </div>

            <div class="container">
              <div class="row g-4 justify-content-center">
                <!-- Character 1 -->
                <div class="col-md-2 col-6">
                  <NuxtLink :to="{ path: '/products', query: { characterId: 'spiderman' } }" class="text-decoration-none">
                    <div class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center">
                      <img src="/assets/img/spiderman.jpg" alt="Spider-Man" class="img-fluid rounded-5 mb-2 theme-img" />
                      <h6 class="mt-2 fw-semibold text-dark">Spider-Man</h6>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Character 2 -->
                <div class="col-md-2 col-6">
                  <NuxtLink :to="{ path: '/products', query: { characterId: 'frozen' } }" class="text-decoration-none">
                    <div class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center">
                      <img src="/assets/img/frozen.jpeg" alt="Frozen" class="img-fluid rounded-5 mb-2 theme-img" />
                      <h6 class="mt-2 fw-semibold text-dark">Frozen</h6>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Character 3 -->
                <div class="col-md-2 col-6">
                  <NuxtLink :to="{ path: '/products', query: { characterId: 'donald-duck' } }" class="text-decoration-none">
                    <div class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center">
                      <img src="/assets/img/donald-duck.png" alt="Donald Duck" class="img-fluid rounded-5 mb-2 theme-img" />
                      <h6 class="mt-2 fw-semibold text-dark">Donald Duck</h6>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Character 4 -->
                <div class="col-md-2 col-6">
                  <NuxtLink :to="{ path: '/products', query: { characterId: 'avengers' } }" class="text-decoration-none">
                    <div class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center">
                      <img src="/assets/img/avengers.jpeg" alt="Avengers" class="img-fluid rounded-5 mb-2 theme-img" />
                      <h6 class="mt-2 fw-semibold text-dark">Avengers</h6>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Character 5 -->
                <div class="col-md-2 col-6">
                  <NuxtLink :to="{ path: '/products', query: { characterId: 'barbie' } }" class="text-decoration-none">
                    <div class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center">
                      <img src="/assets/img/barbie.png" alt="Barbie" class="img-fluid rounded-5 mb-2 theme-img" />
                      <h6 class="mt-2 fw-semibold text-dark">Barbie</h6>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Character 6 -->
                <div class="col-md-2 col-6">
                  <NuxtLink :to="{ path: '/products', query: { characterId: 'super-mario' } }" class="text-decoration-none">
                    <div class="theme-card text-center bg-white p-3 rounded-4 shadow-sm h-100 d-flex flex-column align-items-center">
                      <img src="/assets/img/super-mario.png" alt="Super Mario" class="img-fluid rounded-5 mb-2 theme-img" />
                      <h6 class="mt-2 fw-semibold text-dark">Super Mario</h6>
                    </div>
                  </NuxtLink>
                </div>
              </div>
            </div>
          </section>

          <!-- new arrival -->
          <section id="new-arrival" class="bestsellers-section section py-5">
            <div class="container text-center mb-5" data-aos="fade-up">
              <h2 class="fw-bold">New Arrival</h2>
            </div>

            <div class="container">
              <div class="row g-4">
                <!-- Product 1 -->
                <div class="col-6 col-sm-6 col-md-3">
                  <NuxtLink :to="`/products/1`">
                    <div class="product-card card border-0 shadow-sm rounded-4 p-3 h-100">
                      <img
                        src="/assets/img/offer.jpeg"
                        alt="Product 1"
                        class="img-fluid rounded-3 mb-3"
                        style="height: 200px; object-fit: cover;"
                      />
                      <h5 class="fw-semibold text-dark mb-1">Product Name 1</h5>
                      <div class="mb-2">
                        <span class="text-muted text-decoration-line-through me-2">₹3,999</span>
                        <span class="text-success fw-bold">₹2,499</span>
                      </div>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Product 2 -->
                <div class="col-6 col-sm-6 col-md-3">
                  <NuxtLink :to="`/products/2`">
                    <div class="product-card card border-0 shadow-sm rounded-4 p-3 h-100">
                      <img
                        src="/assets/img/offer.jpeg"
                        alt="Product 2"
                        class="img-fluid rounded-3 mb-3"
                        style="height: 200px; object-fit: cover;"
                      />
                      <h5 class="fw-semibold text-dark mb-1">Product Name 2</h5>
                      <div class="mb-2">
                        <span class="text-muted text-decoration-line-through me-2">₹4,999</span>
                        <span class="text-success fw-bold">₹2,999</span>
                      </div>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Product 3 -->
                <div class="col-6 col-sm-6 col-md-3">
                  <NuxtLink :to="`/products/3`">
                    <div class="product-card card border-0 shadow-sm rounded-4 p-3 h-100">
                      <img
                        src="/assets/img/offer.jpeg"
                        alt="Product 3"
                        class="img-fluid rounded-3 mb-3"
                        style="height: 200px; object-fit: cover;"
                      />
                      <h5 class="fw-semibold text-dark mb-1">Product Name 3</h5>
                      <div class="mb-2">
                        <span class="text-muted text-decoration-line-through me-2">₹2,499</span>
                        <span class="text-success fw-bold">₹1,499</span>
                      </div>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Product 4 -->
                <div class="col-6 col-sm-6 col-md-3">
                  <NuxtLink :to="`/products/4`">
                    <div class="product-card card border-0 shadow-sm rounded-4 p-3 h-100">
                      <img
                        src="/assets/img/offer.jpeg"
                        alt="Product 4"
                        class="img-fluid rounded-3 mb-3"
                        style="height: 200px; object-fit: cover;"
                      />
                      <h5 class="fw-semibold text-dark mb-1">Product Name 4</h5>
                      <div class="mb-2">
                        <span class="text-muted text-decoration-line-through me-2">₹1,999</span>
                        <span class="text-success fw-bold">₹999</span>
                      </div>
                    </div>
                  </NuxtLink>
                </div>
              </div>
            </div>
          </section>

          <!-- best sellers -->
          <section id="best-sellers" class="bestsellers-section section py-5">
            <div class="container text-center mb-5" data-aos="fade-up">
              <h2 class="fw-bold">Best Sellers</h2>
            </div>

            <div class="container">
              <div class="row g-4">
                <!-- Product 1 -->
                <div class="col-6 col-sm-6 col-md-3">
                  <NuxtLink :to="`/products/1`">
                    <div class="product-card card border-0 shadow-sm rounded-4 p-3 h-100">
                      <img
                        src="/assets/img/offer.jpeg"
                        alt="Product 1"
                        class="img-fluid rounded-3 mb-3"
                        style="height: 200px; object-fit: cover;"
                      />
                      <h5 class="fw-semibold text-dark mb-1">Product Name 1</h5>
                      <div class="mb-2">
                        <span class="text-muted text-decoration-line-through me-2">₹3,999</span>
                        <span class="text-success fw-bold">₹2,499</span>
                      </div>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Product 2 -->
                <div class="col-6 col-sm-6 col-md-3">
                  <NuxtLink :to="`/products/2`">
                    <div class="product-card card border-0 shadow-sm rounded-4 p-3 h-100">
                      <img
                        src="/assets/img/offer.jpeg"
                        alt="Product 2"
                        class="img-fluid rounded-3 mb-3"
                        style="height: 200px; object-fit: cover;"
                      />
                      <h5 class="fw-semibold text-dark mb-1">Product Name 2</h5>
                      <div class="mb-2">
                        <span class="text-muted text-decoration-line-through me-2">₹4,999</span>
                        <span class="text-success fw-bold">₹2,999</span>
                      </div>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Product 3 -->
                <div class="col-6 col-sm-6 col-md-3">
                  <NuxtLink :to="`/products/3`">
                    <div class="product-card card border-0 shadow-sm rounded-4 p-3 h-100">
                      <img
                        src="/assets/img/offer.jpeg"
                        alt="Product 3"
                        class="img-fluid rounded-3 mb-3"
                        style="height: 200px; object-fit: cover;"
                      />
                      <h5 class="fw-semibold text-dark mb-1">Product Name 3</h5>
                      <div class="mb-2">
                        <span class="text-muted text-decoration-line-through me-2">₹2,499</span>
                        <span class="text-success fw-bold">₹1,499</span>
                      </div>
                    </div>
                  </NuxtLink>
                </div>

                <!-- Product 4 -->
                <div class="col-6 col-sm-6 col-md-3">
                  <NuxtLink :to="`/products/4`">
                    <div class="product-card card border-0 shadow-sm rounded-4 p-3 h-100">
                      <img
                        src="/assets/img/offer.jpeg"
                        alt="Product 4"
                        class="img-fluid rounded-3 mb-3"
                        style="height: 200px; object-fit: cover;"
                      />
                      <h5 class="fw-semibold text-dark mb-1">Product Name 4</h5>
                      <div class="mb-2">
                        <span class="text-muted text-decoration-line-through me-2">₹1,999</span>
                        <span class="text-success fw-bold">₹999</span>
                      </div>
                    </div>
                  </NuxtLink>
                </div>
              </div>
            </div>
          </section>
        </main>
    </div>
</template>