<script setup>
import { ref } from 'vue'
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
import Main from './components/Main.vue'

const activeView = ref('one')
</script>

<template>
  <div class="layout">
    <Header :activeView="activeView" @update:activeView="activeView = $event" />
    <div class="main-section">
      <Sidebar />
      <main class="content">
        <Main :activeView="activeView" />
      </main>
    </div>
  </div>
</template>

<style scoped>
.layout {
  display: flex;
  flex-direction: column;
  height: 100vh;
  background: #111827;
}

.main-section {
  display: flex;
  flex: 1;
  overflow: hidden;
}

.content {
  flex: 1;
  overflow-y: auto;
  background: #111827;
}
</style>
