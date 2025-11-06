<script setup>
import { ref } from 'vue'

const showDropdown = ref(false)

const toggleDropdown = () => {
  showDropdown.value = !showDropdown.value
}
const handleHome = (msg) => {
  alert(`💚 AhmedStack Docs Notice 💚\n\n🟩 ✨ Designed Alert Message ✨`);
}


const handleAction = (action) => {
  console.log(`You clicked: ${action}`)
  showDropdown.value = false
}
</script>

<template>
  <header class="modern-header">
    <div class="brand">
      <img src="https://cdn-icons-png.flaticon.com/512/5968/5968705.png" alt="logo" class="logo" />
      <h1>AhmedStack Docs</h1>
    </div>

    <nav class="nav-links">
      <a href="#" @click="handleHome('ki hal ha ')">Home</a>
      <a href="#">Docs</a>
      <a href="#">Guides</a>
      <a href="#">About</a>
    </nav>

    <div class="dropdown">
      <button class="dropdown-btn" @click="toggleDropdown">
        Menu
        <span class="arrow" :class="{ open: showDropdown }">▾</span>
      </button>
      <div v-if="showDropdown" class="dropdown-menu">
        <button @click="handleAction('Profile')">Profile</button>
        <button @click="handleAction('Settings')">Settings</button>
        <button @click="handleAction('Logout')">Logout</button>
      </div>
    </div>
  </header>
</template>

<style scoped>
.modern-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: linear-gradient(90deg, #10b981, #059669);
  color: white;
  padding: 0.9rem 2rem;
  border-radius: 12px;
  margin: 1rem;
  box-shadow: 0 8px 20px rgba(0, 128, 0, 0.15);
}

/* 🧩 Brand */
.brand {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.logo {
  width: 36px;
  height: 36px;
  border-radius: 8px;
}

.brand h1 {
  font-size: 1.4rem;
  font-weight: 700;
  letter-spacing: 0.5px;
}

/* 🔗 Navigation */
.nav-links {
  display: flex;
  gap: 1.5rem;
}

.nav-links a {
  color: white;
  text-decoration: none;
  font-weight: 500;
  transition: opacity 0.3s, transform 0.2s;
}

.nav-links a:hover {
  opacity: 0.8;
  transform: translateY(-1px);
}

/* 🔽 Dropdown */
.dropdown {
  position: relative;
}

.dropdown-btn {
  background: white;
  color: #065f46;
  border: none;
  padding: 0.55rem 1.2rem;
  border-radius: 8px;
  font-weight: 600;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 0.35rem;
  box-shadow: 0 2px 5px rgba(0, 128, 0, 0.15);
  transition: background 0.3s, transform 0.2s;
}

.dropdown-btn:hover {
  background: #ecfdf5;
  transform: translateY(-1px);
}

.arrow {
  transition: transform 0.3s;
}

.arrow.open {
  transform: rotate(180deg);
}

/* 📋 Dropdown Menu */
.dropdown-menu {
  position: absolute;
  right: 0;
  top: 120%;
  background: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
  display: flex;
  flex-direction: column;
  min-width: 160px;
  animation: fadeIn 0.25s ease;
}

.dropdown-menu button {
  background: none;
  border: none;
  padding: 0.8rem 1rem;
  text-align: left;
  color: #065f46;
  font-weight: 500;
  cursor: pointer;
  transition: background 0.3s;
}

.dropdown-menu button:hover {
  background: #f0fdf4;
}

/* ✨ Animation */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-5px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
