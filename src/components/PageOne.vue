<script>

import card from '../pages/card.vue';

export default {
  components: {
    card,
  },
  data() {
    return {
      title: "Vue Practice",
      subtitle: "Description",
      description:
        "This page demonstrates a list render using v-for in Vue.js.",
      txt: "This page is used for the counter by using the Options API",
      count: 0,
      StyleBinding: "normal",
      ButtonDisable: false,
      index1: "This one is index one",
      cars: [
        {
          car_name: "Toyota Corolla",
          make: "2005",
          color: "White",
          price: "$8,000",
          engine: "1.8L",
          transmission: "Automatic",
          features: [
            { feature: "Air Conditioning" },
            { feature: "Power Steering" },
            { feature: "Anti-lock Brakes" },
          ],
        },
        {
          car_name: "Honda Civic",
          make: "2010",
          color: "Black",
          price: "$10,500",
          engine: "1.6L",
          transmission: "Manual",
          features: [
            { feature: "Air Conditioning" },
            { feature: "Power Steering" },
            { feature: "Anti-lock Brakes" },
          ],
        },
        {
          car_name: "Suzuki Alto",
          make: "2018",
          color: "Silver",
          price: "$6,200",
          engine: "660cc",
          transmission: "Automatic",
          features: [],
        },
      ],
      myObject: {
        title: 'How to do lists in Vue',
        author: 'Jane Doe',
        publishedAt: '2016-04-10'
      }
    };
  },
  computed: {
  SilverCarsData() {
  return this.cars.filter(car => ["Silver", "Black"].includes(car.color))

  }
   
}
,
  methods: {
    showCarInfo(car) {
      alert(` Car ${car.car_name}\n Make Year ${car.make}`);
    },

    fillterData() {
      return this.cars.filter(car => ["Silver", "Black"].includes(car.color))
    },

    finalCars(){
      const newcar = {
          car_name: "Suzuki Alto",
          make: "2018",
          color: "Silver",
          price: "$6,200",
          engine: "660cc",
          transmission: "Automatic",
          features: [],
        }
           this.cars.push(newcar)   
    return  this.cars
    }
  },
};
</script>

<template>
  <div class="page-wrapper">
    <h1 class="main-title">Vue Practice</h1>
    <h3 class="sub-title">Description</h3>
    <p class="intro-text">
      This page demonstrates a list render using <code>v-for</code> in Vue.js.
    </p>
    <ul>
      <li>List Rendering using v-for</li>
      <li>List Rendering with v-for and Indexing</li>
      <li>List Rendering with v-for and Destructuring</li>
      <li>List Rendering with v-for, Indexing, and Destructuring</li>
      <li>List Rendering with v-for and Nested Looping</li>
      <li>List Rendering with v-for and Object render</li>

      <li>List Rendering with v-for and v-if key And State</li>
      <li>List Rendering with v-for and with a Component</li>
      
    </ul>
    <!-- v-for="(value, key, index) in myObject" -->
    <!-- v-for="(car, index) in cars" -->
    <!-- v-for="car in cars" :key="car.make" -->
    <!-- <h2>{{car.car_name}}</h2> -->
    <div
     v-for="cr in finalCars()"
    >
      <card  :car="cr"/>
    </div>

    <!-- Car List Card -->
    <!-- <div class="card">
      <h2 class="card-title">Cars List</h2>
      <p class="card-description">Static list of cars {{ index1 }}</p>
      <div class="cars-container"> -->
    <!-- v-for="(car, index) in cars" -->
    <!-- v-for="( { name,car_name , make, color, price ,engine, transmission } ,index ) in cars" -->
    <!-- v-if="car.index = 1" -->
    <!-- <div 
          class="car-card" 
          v-for="(car, index) in cars"
          >
          <p><strong>Serial No </strong>{{ index+1 }}</p>
          <h3>{{ car.car_name }}</h3>
          <p><strong>Make Year:</strong> {{ car.make }}</p>
          <p><strong>Color:</strong> {{ car.color }}</p>
          <p><strong>Price:</strong> {{ car.price }}</p>
          <p><strong>Engine:</strong> {{ car.engine }}</p>
          <p><strong>Transmission:</strong> {{ car.transmission }}</p>
          <div class="Child" v-for="feature in car.features">
            <div class="wrapper_features">
              <span>{{ feature.feature }}</span>
            </div>
          </div>
        </div> -->
    <!-- </div> -->
    <!-- </div> -->
  </div>
</template>

<style scoped>
h2{
  color: #e8f4ff;
}
ul li {
  color: white;
}
.Child {
  background-color: #e2e8f0;
  padding: 5px;
  margin-top: 5px;
  display: flex;
  border-radius: 5px;
}
.wrapper_features p {
  display: flex;
}
.page-header {
  text-align: center;
  margin-bottom: 30px;
}

.main-title {
  font-size: 28px;
  font-weight: bold;
  color: #f7f1f1;
}

.sub-title {
  font-size: 20px;
  color: #ffffff;
  margin-top: 5px;
}

.intro-text {
  color: #f3efef;
  margin-top: 10px;
  font-size: 15px;
}

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
.car-card h3 {
  margin: 10px 0;
  color: black;
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
  cursor: pointer;
  transition: all 0.3s ease;
}

.car-card:hover {
  transform: scale(1.05);
  background: #e8f4ff;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
}
</style>
