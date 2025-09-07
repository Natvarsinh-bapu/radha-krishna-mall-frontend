<template>
  <div>
    <main class="main py-5">
      <!-- Page Header -->
      <section class="section text-center mb-3">
        <div class="container">
          <h2 class="fw-bold mb-2">My Account</h2>
          <p class="text-muted mb-0">Manage your profile, orders, and more</p>
        </div>
      </section>

      <!-- Account Section -->
      <section class="section pt-0">
        <div class="container">
          <!-- Profile Info Horizontal Card -->
          <div class="card border-0 shadow-sm rounded-4 p-4 mb-5">
            <div class="d-flex align-items-center">
              <img
                src="/assets/img/offer.jpeg"
                alt="Profile"
                class="rounded-circle me-4"
                width="100"
                height="100"
                style="object-fit: cover;"
              />
              <div>
                <h5 class="fw-bold mb-1">{{ user.name }}</h5>
                <p class="mb-1 text-muted">{{ user.email }}</p>
                <p class="mb-0 text-muted">{{ user.mobile }}</p>
              </div>
              <div class="ms-auto">
                <NuxtLink
                  to="/account/edit"
                  class="btn btn-sm btn-outline-primary rounded-pill"
                >
                  Edit Profile
                </NuxtLink>
              </div>
            </div>
          </div>

          <!-- Dashboard Options (4 card layout) -->
          <div class="row g-4">
            <!-- My Orders -->
            <div class="col-md-6 col-lg-3">
              <NuxtLink to="/" class="text-decoration-none">
                <div class="card border-0 shadow-sm rounded-4 p-4 h-100 text-center">
                  <i class="bi bi-bag fs-2 text-primary mb-3"></i>
                  <h6 class="fw-bold text-dark">My Orders</h6>
                  <p class="text-muted small mb-0">View and track your orders</p>
                </div>
              </NuxtLink>
            </div>

            <!-- Wishlist -->
            <div class="col-md-6 col-lg-3">
              <NuxtLink to="/" class="text-decoration-none">
                <div class="card border-0 shadow-sm rounded-4 p-4 h-100 text-center">
                  <i class="bi bi-heart fs-2 text-danger mb-3"></i>
                  <h6 class="fw-bold text-dark">Wishlist</h6>
                  <p class="text-muted small mb-0">Saved products you love</p>
                </div>
              </NuxtLink>
            </div>

            <!-- Cart -->
            <div class="col-md-6 col-lg-3">
              <NuxtLink to="/" class="text-decoration-none">
                <div class="card border-0 shadow-sm rounded-4 p-4 h-100 text-center">
                  <i class="bi bi-cart fs-2 text-success mb-3"></i>
                  <h6 class="fw-bold text-dark">Cart</h6>
                  <p class="text-muted small mb-0">Products ready to checkout</p>
                </div>
              </NuxtLink>
            </div>

            <!-- Addresses -->
            <div class="col-md-6 col-lg-3">
              <NuxtLink to="/" class="text-decoration-none">
                <div class="card border-0 shadow-sm rounded-4 p-4 h-100 text-center">
                  <i class="bi bi-geo-alt fs-2 text-warning mb-3"></i>
                  <h6 class="fw-bold text-dark">Addresses</h6>
                  <p class="text-muted small mb-0">Manage shipping addresses</p>
                </div>
              </NuxtLink>
            </div>

            <!-- Settings -->
            <div class="col-md-6 col-lg-3">
              <NuxtLink to="/" class="text-decoration-none">
                <div class="card border-0 shadow-sm rounded-4 p-4 h-100 text-center">
                  <i class="bi bi-gear fs-2 text-secondary mb-3"></i>
                  <h6 class="fw-bold text-dark">Settings</h6>
                  <p class="text-muted small mb-0">Account preferences</p>
                </div>
              </NuxtLink>
            </div>

            <!-- Profile -->
            <div class="col-md-6 col-lg-3">
              <NuxtLink to="/" class="text-decoration-none">
                <div class="card border-0 shadow-sm rounded-4 p-4 h-100 text-center">
                  <i class="bi bi-person-circle fs-2 text-info mb-3"></i>
                  <h6 class="fw-bold text-dark">Profile</h6>
                  <p class="text-muted small mb-0">Update personal details</p>
                </div>
              </NuxtLink>
            </div>
          </div>

          <!-- Logout Button -->
          <div class="text-center mt-5">
            <button class="btn btn-outline-danger rounded-pill px-4 py-2">
              <i class="bi bi-box-arrow-right me-2"></i> Logout
            </button>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
const user = {
  name: "John Doe",
  email: "johndoe@email.com",
  mobile: "+91 98765 43210",
};
</script>
