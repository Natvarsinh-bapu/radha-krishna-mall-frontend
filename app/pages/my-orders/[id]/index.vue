<template>
  <div>
    <main class="main py-5">
      <!-- Page Header -->
      <section class="text-center">
        <div class="container">
          <h2 class="fw-bold">Order Details</h2>
          <p class="text-muted">Detailed summary of your order</p>
        </div>
      </section>

      <section class="section">
        <div class="container">
          <!-- Order Card -->
          <div class="card border-0 shadow-sm rounded-4 mb-5">
            <!-- Header -->
            <div
              class="d-flex flex-wrap justify-content-between align-items-center border-bottom p-3"
            >
              <div>
                <h6 class="fw-bold mb-1">Order #{{ order.id }}</h6>
                <p class="mb-0 text-muted small">Placed on {{ order.date }}</p>
              </div>
              <span
                class="badge rounded-pill px-3 py-2"
                :class="statusClass(order.status)"
              >
                {{ order.status }}
              </span>
            </div>

            <!-- Shipping & Payment -->
            <div class="row g-4 p-3">
              <div class="col-md-6">
                <h6 class="fw-bold">Shipping Address</h6>
                <p class="mb-1">{{ order.shipping.name }}</p>
                <p class="mb-1">{{ order.shipping.street }}</p>
                <p class="mb-1">
                  {{ order.shipping.city }}, {{ order.shipping.state }} -
                  {{ order.shipping.pincode }}
                </p>
                <p class="mb-0 text-muted">Phone: {{ order.shipping.mobile }}</p>
              </div>
              <div class="col-md-6">
                <h6 class="fw-bold">Payment Method</h6>
                <p class="mb-0">{{ order.paymentMethod }}</p>
              </div>
            </div>

            <!-- Items -->
            <div class="p-3 border-top">
              <h6 class="fw-bold mb-3">Items in this Order</h6>
              <div
                v-for="(item, i) in order.items"
                :key="i"
                class="d-flex align-items-center mb-3"
              >
                <img
                  src="/assets/img/offer.jpeg"
                  :alt="item.name"
                  class="rounded-3"
                  style="width: 80px; height: 80px; object-fit: cover;"
                />
                <div class="ms-3 flex-grow-1">
                  <h6 class="fw-semibold text-dark mb-1">{{ item.name }}</h6>
                  <p class="text-muted small mb-0">{{ item.shortDesc }}</p>
                </div>
                <div class="text-end">
                  <p class="mb-1 fw-bold">₹{{ item.price }}</p>
                  <p class="text-muted small">x {{ item.quantity }}</p>
                </div>
              </div>
            </div>

            <!-- Order Summary -->
            <div class="p-3 border-top">
              <h6 class="fw-bold mb-3">Order Summary</h6>
              <div class="d-flex justify-content-between mb-2">
                <span>Subtotal</span>
                <span>₹{{ order.subtotal }}</span>
              </div>
              <div class="d-flex justify-content-between mb-2">
                <span>Shipping</span>
                <span>₹{{ order.shippingCharge }}</span>
              </div>
              <div class="d-flex justify-content-between text-success mb-2">
                <span>Discount</span>
                <span>- ₹{{ order.discount }}</span>
              </div>
              <hr />
              <div class="d-flex justify-content-between fw-bold mb-0">
                <span>Total</span>
                <span>₹{{ order.total }}</span>
              </div>
            </div>

            <!-- Footer Actions -->
            <div
              class="d-flex flex-wrap justify-content-between align-items-center border-top p-3"
            >
              <div>
                <NuxtLink
                  to="/my-orders/123/track"
                  class="btn btn-sm btn-success rounded-pill me-2"
                >
                  <i class="bi bi-truck me-1"></i> Track Order
                </NuxtLink>
                <button class="btn btn-sm btn-outline-secondary rounded-pill">
                  <i class="bi bi-download me-1"></i> Download Invoice
                </button>
              </div>
              <NuxtLink to="/my-orders" class="text-decoration-none small text-muted">
                ← Back to Orders
              </NuxtLink>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref } from "vue";

const order = ref({
  id: "1001",
  date: "20 Sep 2025",
  status: "Delivered",
  paymentMethod: "Cash on Delivery",
  shippingCharge: 199,
  discount: 500,
  subtotal: 4498,
  total: 4197,
  shipping: {
    name: "John Doe",
    street: "123 Park Street",
    city: "Mumbai",
    state: "Maharashtra",
    pincode: "400001",
    mobile: "+91 98765 43210",
  },
  items: [
    {
      name: "Toy Car",
      shortDesc: "A cool racing car for kids",
      price: 1499,
      quantity: 1,
    },
    {
      name: "Barbie Doll",
      shortDesc: "Beautiful doll with accessories",
      price: 2999,
      quantity: 1,
    },
  ],
});

// Dynamic status classes
const statusClass = (status) => {
  switch (status) {
    case "Delivered":
      return "bg-success text-white";
    case "Shipped":
      return "bg-info text-white";
    case "Pending":
      return "bg-warning text-dark";
    case "Cancelled":
      return "bg-danger text-white";
    default:
      return "bg-secondary text-white";
  }
};
</script>
