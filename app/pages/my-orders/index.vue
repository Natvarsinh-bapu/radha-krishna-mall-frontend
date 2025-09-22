<template>
  <div>
    <main class="main py-5">
      <!-- Page Header -->
      <section class="section text-center mb-4">
        <div class="container">
          <h2 class="fw-bold">My Orders</h2>
          <p class="text-muted">Track and manage your past orders</p>
        </div>
      </section>

      <!-- Orders Section -->
      <section class="section">
        <div class="container">
          <div v-if="orders.length > 0" class="order-list">
            <div
              v-for="(order, index) in orders"
              :key="index"
              class="card border-0 shadow-sm rounded-4 mb-4"
            >
              <!-- Order Header -->
              <div
                class="d-flex flex-wrap justify-content-between align-items-center border-bottom p-3"
              >
                <div>
                  <h6 class="fw-bold mb-1">Order #{{ order.id }}</h6>
                  <p class="mb-0 text-muted small">Placed on {{ order.date }}</p>
                </div>
                <div class="text-end">
                  <span
                    class="badge rounded-pill px-3 py-2"
                    :class="statusClass(order.status)"
                  >
                    {{ order.status }}
                  </span>
                </div>
              </div>

              <!-- Order Items -->
              <div class="p-3">
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
                    <h6 class="fw-semibold text-dark mb-1">
                      {{ item.name }}
                    </h6>
                    <p class="text-muted small mb-0">{{ item.shortDesc }}</p>
                  </div>
                  <div class="text-end">
                    <p class="mb-1 fw-bold">₹{{ item.price }}</p>
                    <p class="text-muted small">x {{ item.quantity }}</p>
                  </div>
                </div>
              </div>

              <!-- Order Footer -->
              <div
                class="d-flex flex-wrap justify-content-between align-items-center border-top p-3"
              >
                <p class="fw-bold mb-0">Total: ₹{{ order.total }}</p>
                <div>
                  <NuxtLink
                    :to="`/my-orders/${order.id}`"
                    class="btn btn-sm btn-outline-primary rounded-pill me-2"
                  >
                    View Details
                  </NuxtLink>
                  <NuxtLink
                    :to="`/my-orders/${order.id}/track`"
                    class="btn btn-sm btn-success rounded-pill"
                  >
                    Track Order
                  </NuxtLink>
                </div>
              </div>
            </div>
          </div>

          <!-- Empty State -->
          <div v-else class="text-center py-5">
            <h5 class="text-muted">You haven't placed any orders yet</h5>
            <NuxtLink
              to="/shop"
              class="btn btn-primary mt-3 rounded-pill px-4 py-2"
            >
              Start Shopping
            </NuxtLink>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref } from "vue";

const orders = ref([
  {
    id: "1001",
    date: "20 Sep 2025",
    status: "Delivered",
    total: 3998,
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
        price: 2499,
        quantity: 1,
      },
    ],
  },
  {
    id: "1002",
    date: "15 Sep 2025",
    status: "Shipped",
    total: 1499,
    items: [
      {
        name: "Remote Drone",
        shortDesc: "Mini drone with camera",
        price: 1499,
        quantity: 1,
      },
    ],
  },
]);

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
