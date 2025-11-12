<template>
  <div class="page-wrapper">
 

    <div class="card">
      <h2 class="card-title">Counter Demo</h2>
      <p class="card-description">{{ txt }}</p>

      <div class="counter-wrapper">
        <div class="counter-display">
          <div class="counter-label">{{ count > 1 ? "Ahmed Raza" : "Chal Dafa ho" }}</div>
          <div class="counter-value">{{ count }}</div>
        </div>

        <div class="counter-controls">
          <button class="counter-btn decrement-btn" @click="decrement">−</button>
          <button :disabled="ButtonDisable" class="counter-btn increment-btn" @click="increment">+</button>
        </div>
      </div>
    </div>

       <div class="card">
      <h2 class="card-title">Attribute Bindings</h2>
      <div :class="['binding-container', StyleBinding]">
        <h3 :="objectOfAttrs" class="binding-title">Dynamic Attribute Binding</h3>
        <div :id="`list-${count}`" class="binding-item">
          <p class="item-text">ID: list-{{ count }}</p>
        </div>
        <button class="primary-btn" @click="handledisk(count)">Call Function</button>
        <div class="status-display">
          <span class="label">Current Status:</span>
          <span class="value">{{ StyleBinding }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      txt: "This page is used for the counter By using the option api",
      count: 0,
      StyleBinding: "normal",
      ButtonDisable: false,
      objectOfAttrs: {
        id: "container",
        class: "wrapper",
      },
    };
  },
  methods: {
    increment() {
      this.count++;

      if (this.count >= 10) {
        this.ButtonDisable = true;
        this.StyleBinding = "warning";
      } else if (this.count > 5) {
        this.StyleBinding = "success";
        this.ButtonDisable = false;
      } else {
        this.StyleBinding = "normal";
      }
    },
    decrement() {
      this.count--;

      if (this.count < 0) {
        this.StyleBinding = "danger";
      } else if (this.count < 10) {
        this.ButtonDisable = false;
      }
    },
    handledisk(num) {
      alert("Function Called with the value " + num / 2);
    },
  },
};
</script>

<style scoped>
.page-wrapper {
  padding: 2rem;
  max-width: 900px;
  margin: 0 auto;
}

.card {
  background: #1f2937;
  border: 1px solid #374151;
  border-radius: 8px;
  padding: 2rem;
  margin-bottom: 1.5rem;
}

.card-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: #f9fafb;
  margin: 0 0 1rem;
}

.card-description {
  color: #9ca3af;
  font-size: 0.9375rem;
  margin: 0 0 1.5rem;
}

.binding-container {
  padding: 1.5rem;
  border-radius: 6px;
  border: 1px solid #374151;
  background: #111827;
  transition: all 0.2s;
}

.binding-container.success {
  background: #064e3b;
  border-color: #10b981;
}

.binding-container.warning {
  background: #78350f;
  border-color: #f59e0b;
}

.binding-container.danger {
  background: #7f1d1d;
  border-color: #ef4444;
}

.binding-title {
  font-size: 1rem;
  font-weight: 600;
  color: #e5e7eb;
  margin: 0 0 1rem;
}

.binding-item {
  margin-bottom: 1rem;
}

.item-text {
  color: #9ca3af;
  font-size: 0.875rem;
  margin: 0;
}

.primary-btn {
  padding: 0.5rem 1rem;
  background: #3b82f6;
  color: #fff;
  border: none;
  border-radius: 6px;
  font-size: 0.875rem;
  font-weight: 500;
  cursor: pointer;
  transition: background 0.2s;
  margin-bottom: 1rem;
}

.primary-btn:hover {
  background: #2563eb;
}

.status-display {
  display: flex;
  gap: 0.5rem;
  font-size: 0.875rem;
}

.label {
  color: #9ca3af;
  font-weight: 500;
}

.value {
  color: #f9fafb;
  font-weight: 600;
}

.counter-wrapper {
  background: #111827;
  border: 1px solid #374151;
  border-radius: 8px;
  padding: 2rem;
}

.counter-display {
  text-align: center;
  margin-bottom: 2rem;
}

.counter-label {
  font-size: 0.875rem;
  color: #9ca3af;
  font-weight: 500;
  margin-bottom: 0.5rem;
}

.counter-value {
  font-size: 3.5rem;
  font-weight: 700;
  color: #f9fafb;
  line-height: 1;
}

.counter-controls {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.counter-btn {
  width: 56px;
  height: 56px;
  border: none;
  border-radius: 8px;
  font-size: 1.5rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
}

.counter-btn:disabled {
  opacity: 0.4;
  cursor: not-allowed;
}

.increment-btn {
  background: #3b82f6;
  color: #fff;
}

.increment-btn:hover:not(:disabled) {
  background: #2563eb;
}

.decrement-btn {
  background: #ef4444;
  color: #fff;
}

.decrement-btn:hover:not(:disabled) {
  background: #dc2626;
}
</style>
