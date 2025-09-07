<template>
  <div>
    <main class="main py-5">
      <!-- Page Header -->
      <section class="section text-center">
        <div class="container">
          <h2 class="fw-bold">Shopping Cart</h2>
          <p class="text-muted">Review your items before checkout</p>
        </div>
      </section>

      <!-- Cart Items -->
      <section class="section">
        <div class="container">
          <div class="row">
            <!-- Cart List -->
            <div class="col-lg-8">
              <div v-if="cart.length > 0" class="cart-list">
                <div
                  v-for="(item, index) in cart"
                  :key="index"
                  class="card border-0 shadow-sm rounded-4 mb-3 p-3"
                >
                  <div class="d-flex align-items-center">
                    <!-- Image -->
                    <img
                      src="/assets/img/offer.jpeg"
                      :alt="item.name"
                      class="rounded-3"
                      style="width: 100px; height: 100px; object-fit: cover;"
                    />

                    <!-- Info -->
                    <div class="ms-3 flex-grow-1">
                      <h6 class="fw-semibold text-dark">{{ item.name }}</h6>
                      <p class="mb-1 text-muted">Price: ₹{{ item.price }}</p>

                      <!-- Quantity Controls -->
                      <div class="d-flex align-items-center">
                        <button
                          class="btn btn-sm btn-outline-secondary rounded-pill"
                          @click="decreaseQty(index)"
                        >-</button>
                        <span class="mx-2">{{ item.quantity }}</span>
                        <button
                          class="btn btn-sm btn-outline-secondary rounded-pill"
                          @click="increaseQty(index)"
                        >+</button>
                      </div>
                    </div>

                    <!-- Remove -->
                    <button
                      class="btn btn-sm btn-outline-danger rounded-pill ms-3"
                      @click="removeItem(index)"
                    >
                      <i class="bi bi-trash"></i>
                    </button>
                  </div>
                </div>
              </div>

              <!-- Empty Cart -->
              <div v-else class="text-center py-5">
                <h5 class="text-muted">Your cart is empty</h5>
                <NuxtLink
                  to="/shop"
                  class="btn btn-danger mt-3 rounded-pill px-4 py-2"
                >
                  Start Shopping
                </NuxtLink>
              </div>
            </div>

            <!-- Cart Summary -->
            <div class="col-lg-4">
              <div class="card border-0 shadow-sm rounded-4 p-4">
                <h5 class="fw-bold mb-3">Order Summary</h5>
                <div class="d-flex justify-content-between mb-2">
                  <span>Subtotal</span>
                  <span>₹{{ subtotal }}</span>
                </div>
                <div class="d-flex justify-content-between mb-2">
                  <span>Shipping</span>
                  <span>₹{{ shipping }}</span>
                </div>
                <hr />
                <div class="d-flex justify-content-between fw-bold mb-3">
                  <span>Total</span>
                  <span>₹{{ total }}</span>
                </div>
                <NuxtLink
                  to="/checkout"
                  class="btn btn-success w-100 rounded-pill py-2"
                >
                  Proceed to Checkout
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const cart = ref([
  { name: "Toy Car", price: 1499, quantity: 1 },
  { name: "Barbie Doll", price: 2499, quantity: 2 },
]);

// Computed values
const subtotal = computed(() =>
  cart.value.reduce((sum, item) => sum + item.price * item.quantity, 0)
);
const shipping = computed(() => (cart.value.length > 0 ? 199 : 0));
const total = computed(() => subtotal.value + shipping.value);

// Methods
const increaseQty = (index) => {
  cart.value[index].quantity++;
};
const decreaseQty = (index) => {
  if (cart.value[index].quantity > 1) {
    cart.value[index].quantity--;
  }
};
const removeItem = (index) => {
  cart.value.splice(index, 1);
};
</script>
