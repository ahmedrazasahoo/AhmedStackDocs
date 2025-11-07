<script setup>
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
import Main from './components/Main.vue'
</script>

<template>
  <div class="layout">
    <Header />
    <div class="main-section">
      <Sidebar />
      <main class="content">
        <h2>WELCOME TO PRACTICE</h2>
          <Main/>
      </main>
    </div>
  </div>
</template>

<style scoped>
.layout {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.main-section {
  display: flex;
  flex: 1;
}

.content {
  flex: 1;
  padding: 2rem;
  background: #f9fafb;
}
</style>
