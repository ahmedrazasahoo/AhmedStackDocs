<script>
export default{

  props:{
    car:Object
  }
}

</script>

<template>

<div class="card">
    <h3> Name{{ car.car_name }}</h3>
</div>

</template>

<style scoped>
.card {
  background: #fff;
  border-radius: 15px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.15);
  padding: 20px;
  margin-bottom: 20px;
}
.car-card h3 {
    color: #fff;
  margin: 10px 0;
}
</style>