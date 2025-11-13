<script>
export default {
  data() {
    return {
      nameData: "",
      age:0
    };
  },
};
</script>

<template>
  <div class="page-wrapper">
    <h1 class="main-title">Vue Form Input Bindings</h1>
    <p class="intro-text">
      Demonstrates how <code>v-model</code> keeps form inputs in sync with Vue data.
    </p>

    <ul class="features-list">
      <li><strong>v-model</strong> automatically binds input value to Vue data.</li>
      <li>No need for manual event listeners like <code>@input</code>.</li>
      <li>Works seamlessly with text, checkbox, radio, and select elements.</li>
    </ul>

    <div class="form-wrapper">
      <form @submit.prevent>
        <div class="input-wrapper">
          <label >Enter your name:</label>
          <input type="text" v-model="nameData" placeholder="Type your name here..."
        />
        </div>
        <div class="input-wrapper">
          <label >Age:</label>
          <input type="number" v-model="age" placeholder="Type your age here..."
          />
        </div>

    
      </form>

      <div v-if="nameData" class="output-box">
        <h3>Hello, <span>{{ nameData }}</span> {{ age }}</h3>
      </div>
      
      <div v-if="age" class="output-box">
           <h3>Age, <span> {{ age }}</span></h3>

         </div>
    </div>
  </div>
</template>

<style scoped>
.input-wrapper{
  display: block;
  background: #332727;
  padding: 20px;  
  border-radius: 20px;
  height: 50px;
  width: 100%;
}
.page-wrapper {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  padding: 40px;
  background: #1a1a2e;
  min-height: 100vh;
  color: #f3f3f3;
}

.main-title {
  font-size: 32px;
  font-weight: 700;
  margin-bottom: 10px;
  color: #e94560;
  text-align: center;
}

.intro-text {
  font-size: 16px;
  margin-bottom: 20px;
  text-align: center;
  color: #dcdde1;
}

.features-list {
  list-style: none;
  padding: 0;
  margin: 20px auto 40px;
  max-width: 600px;
}

.features-list li {
  margin: 8px 0;
  padding: 8px 12px;
  background: #162447;
  border-radius: 10px;
  line-height: 1.4;
}

.form-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.form-label {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 10px;
  color: #f76c6c;
}

.form-input {
  width: 300px;
  padding: 12px 16px;
  font-size: 16px;
  border: 2px solid #0f3460;
  border-radius: 10px;
  background: #162447;
  color: #fff;
  outline: none;
  transition: 0.3s ease;
}

.form-input::placeholder {
  color: #aaa;
}

.form-input:focus {
  border-color: #e94560;
  box-shadow: 0 0 8px #e9456080;
}

.output-box {
  margin-top: 25px;
  background: #162447;
  padding: 15px 25px;
  border-radius: 12px;
  box-shadow: 0 0 8px #0f346060;
}

.output-box h3 {
  color: #e94560;
  font-weight: 600;
}

.output-box span {
  color: #fff;
}
</style>
