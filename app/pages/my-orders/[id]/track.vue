<template>
  <div>
    <main class="main py-5">
      <!-- Page Header -->
      <section class="section text-center mb-4">
        <div class="container">
          <h2 class="fw-bold">Track Order</h2>
          <p class="text-muted">Live status of your order</p>
        </div>
      </section>

      <section class="section">
        <div class="container">
          <!-- Order Info -->
          <div class="card border-0 shadow-sm rounded-4 mb-4 p-4">
            <div class="d-flex flex-wrap justify-content-between align-items-center">
              <div>
                <h6 class="fw-bold mb-1">Order #{{ order.id }}</h6>
                <p class="mb-0 text-muted small">Placed on {{ order.date }}</p>
              </div>
              <span class="badge rounded-pill px-3 py-2" :class="statusClass(order.status)">
                {{ order.status }}
              </span>
            </div>
          </div>

          <!-- Tracking Timeline -->
          <div class="card border-0 shadow-sm rounded-4 p-4">
            <h6 class="fw-bold mb-4">Order Progress</h6>

            <div class="timeline">
              <div
                v-for="(step, index) in steps"
                :key="index"
                class="timeline-step d-flex align-items-start mb-4"
              >
                <!-- Step Icon -->
                <div
                  class="timeline-icon rounded-circle d-flex align-items-center justify-content-center me-3"
                  :class="{
                    'bg-success text-white': step.completed,
                    'bg-light text-muted': !step.completed
                  }"
                  style="width: 40px; height: 40px;"
                >
                  <i :class="step.icon"></i>
                </div>

                <!-- Step Content -->
                <div class="flex-grow-1">
                  <h6 class="fw-semibold mb-1" :class="step.completed ? 'text-dark' : 'text-muted'">
                    {{ step.label }}
                  </h6>
                  <p class="small text-muted mb-0">
                    {{ step.date ? step.date : "Pending" }}
                  </p>
                </div>
              </div>
            </div>
          </div>

          <!-- Footer Actions -->
          <div class="text-center mt-4">
            <NuxtLink to="/my-orders" class="btn btn-outline-secondary rounded-pill px-4">
              ← Back to Orders
            </NuxtLink>
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
  status: "Out for Delivery",
});

// Timeline steps
const steps = ref([
  {
    label: "Order Placed",
    icon: "bi bi-cart-check",
    date: "20 Sep 2025, 10:30 AM",
    completed: true,
  },
  {
    label: "Shipped",
    icon: "bi bi-truck",
    date: "21 Sep 2025, 4:00 PM",
    completed: true,
  },
  {
    label: "Out for Delivery",
    icon: "bi bi-box-seam",
    date: "22 Sep 2025, 9:00 AM",
    completed: true,
  },
  {
    label: "Delivered",
    icon: "bi bi-house-check",
    date: null, // not delivered yet
    completed: false,
  },
]);

// Dynamic status classes
const statusClass = (status) => {
  switch (status) {
    case "Delivered":
      return "bg-success text-white";
    case "Out for Delivery":
      return "bg-info text-white";
    case "Shipped":
      return "bg-primary text-white";
    case "Pending":
      return "bg-warning text-dark";
    case "Cancelled":
      return "bg-danger text-white";
    default:
      return "bg-secondary text-white";
  }
};
</script>

<style scoped>
.timeline {
  border-left: 2px solid #dee2e6;
  margin-left: 20px;
  padding-left: 20px;
}
.timeline-step:last-child {
  margin-bottom: 0;
}
</style>
