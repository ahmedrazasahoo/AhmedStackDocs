<script>
export default {
  data() {
    return {
      car: {
        car_name: "Toyota",
        car_description: "This is a good car"
      }
    };
  }
};
</script>

<template>
  <div>
    <h1>Name: {{ car.car_name }}</h1>
    <p>Description: {{ car.car_description }}</p>
  </div>
</template>

<style scoped>
h1 {
  color: #333;
  font-size: 24px;
  margin-bottom: 10px;
  text-align: center;
}
p {
  color: #666;
  font-size: 16px;
  line-height: 1.5;
  text-align: center;
}
</style>
