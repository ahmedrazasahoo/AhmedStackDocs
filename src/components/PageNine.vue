<script>
export default {
  data() {
    return {
      title: "Page Nine",
      description: "This is page nine content"
    };
  }
};
</script>

<template>
  <div class="page-wrapper">
    <h1 class="main-title">{{ title }}</h1>
    <p class="intro-text">{{ description }}</p>
    <div class="content-box">
      <p>Content for page nine goes here.</p>
    </div>
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
