<template>
    <header id="header" class="header d-flex align-items-center fixed-top">
        <div class="header-container position-relative d-flex align-items-center justify-content-between">
            <a href="/" class="logo d-flex align-items-center me-auto me-xl-0">
                <img src="/assets/img/logo.jpg" alt="">
            </a>

            <nav id="navmenu" class="navmenu">
              <ul class="nav justify-content-center gap-3">
                <!-- Main Links -->
                <li class="nav-item">
                    <NuxtLink to="/" exact-active-class="active" class="nav-link">
                    Home
                    </NuxtLink>
                </li>
                <li class="nav-item">
                    <NuxtLink to="/products" exact-active-class="active" class="nav-link">
                    Products
                    </NuxtLink>
                </li>
                <li class="nav-item">
                    <NuxtLink to="/contact" exact-active-class="active" class="nav-link">
                    Contact
                    </NuxtLink>
                </li>

                <!-- Extra Links with Icons -->
                <li class="nav-item">
                  <NuxtLink to="/wishlist" exact-active-class="active" class="nav-link">
                    <div class="position-relative d-inline-block">
                      <i class="bi bi-heart fs-4"></i>
                    </div>
                  </NuxtLink>
                </li>

                <li class="nav-item">
                  <NuxtLink to="/cart" exact-active-class="active" class="nav-link">
                    <div class="position-relative d-inline-block">
                      <i class="bi bi-cart fs-4"></i>
                      <!-- Badge -->
                      <span
                        class="position-absolute top-0 start-100 translate-middle bg-danger text-white rounded-circle d-flex justify-content-center align-items-center"
                        style="width: 18px; height: 18px; font-size: 0.7rem;"
                      >
                        2
                      </span>
                    </div>
                  </NuxtLink>
                </li>

                <li class="nav-item">
                  <NuxtLink to="/account" exact-active-class="active" class="nav-link">
                    <div class="position-relative d-inline-block">
                      <i class="bi bi-person fs-4"></i>
                    </div>
                  </NuxtLink>
                </li>
              </ul>

              <i class="mobile-nav-toggle d-xl-none bi bi-list"></i>
            </nav>
        </div>
    </header>
</template>