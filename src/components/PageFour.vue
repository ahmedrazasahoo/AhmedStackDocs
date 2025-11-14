<script>
import api from './api.vue';
export default {


  components:{
    api
  }
 ,
  data() {
    return {
      title: "Page Four",
      description: "This is page four content"
    };
  }
};
</script>

<template>
  <div class="page-wrapper">
  <h1 class="main-title">Vue Watchers</h1>

    <ul class="features-list">
   
      <li>No need for manual event listeners like <code>@input</code>.</li>
   
    </ul>

    <api/>

 
  </div>
</template>

<style scoped>
.page-wrapper {
  font-family: sans-serif;
  padding: 30px;
  background: #1a1a2e;
  min-height: 100vh;
  color: #fff;
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

.content-box {
  background: #162447;
  padding: 20px;
  border-radius: 12px;
  margin-top: 20px;
}
</style>
