<template>
  <footer id="footer" class="footer">
    <div class="container footer-top">
      <div class="row gy-4 justify-content-center text-center">
        <div class="col-lg-6 col-md-8 col-12 d-flex flex-column align-items-center">
          <!-- Logo -->
          <a href="/" class="logo d-flex justify-content-center mb-4">
            <img src="/assets/img/logo.jpg" alt="Logo" height="100">
          </a>

          <!-- Contact -->
          <div class="footer-contact">
            <p>A108 Adam Street</p>
            <p>New York, NY 535022</p>
            <p class="mt-3"><strong>Phone:</strong> <span>+1 5589 55488 55</span></p>
            <p><strong>Email:</strong> <span>info@example.com</span></p>
          </div>

          <!-- Social Links -->
          <div class="social-links d-flex justify-content-center align-items-center gap-3 mt-4">
            <a href="#" class="social-icon">
              <img src="/assets/img/instagram.png" alt="Instagram">
            </a>
            <a href="#" class="social-icon">
              <img src="/assets/img/whatsapp.png" alt="WhatsApp">
            </a>
            <a href="#" class="social-icon">
              <img src="/assets/img/youtube.png" alt="YouTube">
            </a>
            <a href="#" class="social-icon">
              <img src="/assets/img/telegram.png" alt="Telegram">
            </a>
            <a href="#" class="social-icon">
              <img src="/assets/img/facebook.png" alt="Facebook">
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Copyright -->
    <div class="container copyright text-center mt-4">
      <p>
        © <span>Copyright</span>
        <strong class="px-1 sitename">Radha Krishna Mall</strong>
        <span>All Rights Reserved</span>
      </p>

      <!-- Links -->
      <div class="footer-links mt-3">
        <NuxtLink to="/privacy-policy" class="text-decoration-none text-muted mx-2">Privacy Policy</NuxtLink> |
        <NuxtLink to="/terms-and-conditions" class="text-decoration-none text-muted mx-2">Terms & Conditions</NuxtLink>
      </div>

      <div class="credits">
        Designed by <a href="">bapu</a>
      </div>
    </div>
  </footer>
</template>
