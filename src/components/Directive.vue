<script>
export default {
  data() {
    return {
      name: "Ahmed",
      isActive: true,
      classObject: {
        "bg-wrapper": true,
        "text-danger": true,
      },
    };
  },
  methods: {
    handleError() {
      this.classObject["bg-wrapper"] = true;
      console.log("Show in the console");
    },
    reset() {
      this.classObject["bg-wrapper"] = false;
      console.log("Show in the console and Reset This One");
    },
  },
};
</script>

<template>
  <div class="page-container">
    <div class="page-header">
      <h2 class="page-title">Class Directive Demo</h2>
      <p class="page-greeting">Welcome, {{ name }}</p>
    </div>

    <div class="demo-grid">
      <div class="demo-box" :class="{ 'is-active': isActive }">
        <p class="box-description">Dynamic class binding based on active state</p>
      </div>

      <div class="demo-box" :class="classObject">
        <p class="box-description">Dynamic class binding using object</p>
      </div>
    </div>

    <div class="button-group">
      <button class="action-btn error-btn" @click="handleError">Show Error</button>
      <button class="action-btn reset-btn" @click="reset">Reset</button>
    </div>
  </div>
</template>

<style scoped>
.page-container {
  padding: 2rem;
  max-width: 900px;
  margin: 0 auto;
}

.page-header {
  margin-bottom: 2rem;
}

.page-title {
  font-size: 1.5rem;
  font-weight: 600;
  color: #f9fafb;
  margin: 0 0 0.5rem;
}

.page-greeting {
  color: #9ca3af;
  font-size: 0.9375rem;
  margin: 0;
}

.demo-grid {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-bottom: 2rem;
}

.demo-box {
  background: #1f2937;
  border: 1px solid #374151;
  border-radius: 8px;
  padding: 1.5rem;
  transition: all 0.2s;
}

.demo-box.is-active {
  background: #7f1d1d;
  border-color: #ef4444;
}

.demo-box.bg-wrapper {
  background: #064e3b;
  border-color: #10b981;
}

.demo-box.text-danger {
  background: #7f1d1d;
  border-color: #ef4444;
}

.box-description {
  color: #e5e7eb;
  font-size: 0.9375rem;
  margin: 0;
}

.button-group {
  display: flex;
  gap: 1rem;
}

.action-btn {
  padding: 0.625rem 1.25rem;
  border: none;
  border-radius: 6px;
  font-size: 0.875rem;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s;
}

.error-btn {
  background: #ef4444;
  color: #fff;
}

.error-btn:hover {
  background: #dc2626;
}

.reset-btn {
  background: #374151;
  color: #f9fafb;
  border: 1px solid #4b5563;
}

.reset-btn:hover {
  background: #4b5563;
}
</style>
