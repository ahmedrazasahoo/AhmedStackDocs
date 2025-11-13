<script>
export default {
  data() {
    return {
      txt: "This page is used for the counter by using the Options API",
      count: 0,
      StyleBinding: "normal",
      ButtonDisable: false,
      cars: [
        {
          car_name: "Toyota Corolla",
          make: "2005",
        },
        {
          car_name: "Honda Civic",
          make: "2010",
        },
        {
          car_name: "Suzuki Alto",
          make: "2018",
        },
      ],
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

<template>
  <div class="page-wrapper">
    <h1>Vue Practice</h1>
    <h3>Description</h3>

    <!-- Car List Card -->
    <div class="card">
      <h2 class="card-title">Cars List</h2>
      <p class="card-description">Static list of cars</p>

      <div class="cars-container">
        <div class="car-card" v-for="(car, index) in cars" :key="index">
          <h3>{{ car.car_name }}</h3>
          <p>Make Year: {{ car.make }}</p>
        </div>
      </div>
    </div>

    <!-- Counter Card -->
    <div class="card">
      <h2 class="card-title">Counter Demo</h2>
      <p class="card-description">{{ txt }}</p>

      <div class="counter-wrapper">
        <div class="counter-display">
          <div class="counter-label">
            {{ count > 1 ? "Ahmed Raza" : "Chal Dafa Ho" }}
          </div>
          <div class="counter-value">{{ count }}</div>
        </div>

        <div class="counter-controls">
          <button class="counter-btn decrement-btn" @click="decrement">−</button>
          <button
            :disabled="ButtonDisable"
            class="counter-btn increment-btn"
            @click="increment"
          >
            +
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.page-wrapper {
  font-family: sans-serif;
  padding: 20px;
}

.card {
  background: #fff;
  border-radius: 15px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.15);
  padding: 20px;
  margin-bottom: 20px;
}

.card-title {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-description {
  color: #666;
  margin-bottom: 15px;
}

.cars-container {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}

.car-card {
  background: #f8f9fa;
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 15px;
  width: 180px;
  text-align: center;
}

.counter-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.counter-display {
  text-align: center;
  margin-bottom: 15px;
}

.counter-label {
  font-weight: bold;
}

.counter-controls {
  display: flex;
  gap: 10px;
}

.counter-btn {
  background: #007bff;
  color: white;
  border: none;
  padding: 8px 15px;
  font-size: 18px;
  border-radius: 8px;
  cursor: pointer;
}

.counter-btn:disabled {
  background: gray;
  cursor: not-allowed;
}
</style>

