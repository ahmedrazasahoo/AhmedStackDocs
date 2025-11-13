<script setup>
import { ref, defineProps, defineEmits } from 'vue'

const props = defineProps({
  activeView: {
    type: String,
    default: 'one'
  }
})

const emit = defineEmits(['update:activeView'])

const showDropdown = ref(false)

const handleHome = () => {
  alert(`💚 AhmedStack Docs Notice 💚\n\n🟩 ✨ Designed Alert Message ✨`);
}

const setActiveView = (view) => {
  emit('update:activeView', view)
  showDropdown.value = false
}

const toggleDropdown = () => {
  showDropdown.value = !showDropdown.value
}

const getViewLabel = (view) => {
  const labels = {
    'one': 'Counter',
    'two': 'Directive',
    'three': 'Both',
    'pageOne': 'Page One',
    'pageTwo': 'Page Two',
    'pageThree': 'Page Three'
  }
  return labels[view] || 'Select View'
}
</script>

<template>
  <header class="header">
    <div class="header-container">
      <div class="brand">
        <img src="https://cdn-icons-png.flaticon.com/512/5968/5968705.png" alt="logo" class="logo" />
        <h1 class="brand-title">AhmedStack Docs</h1>
      </div>

      <nav class="nav">
        <a href="#" class="nav-link" @click="handleHome">Home</a>
        <a href="#" class="nav-link">Docs</a>
        <a href="#" class="nav-link">Guides</a>
        <a href="#" class="nav-link">About</a>
      </nav>

      <div class="dropdown">
        <button class="dropdown-toggle" @click="toggleDropdown">
          <span>{{ getViewLabel(activeView) }}</span>
          <span class="arrow" :class="{ open: showDropdown }">▾</span>
        </button>
        <div v-if="showDropdown" class="dropdown-menu">
          <button 
            class="dropdown-item" 
            :class="{ active: activeView === 'one' }"
            @click="setActiveView('one')"
          >
            Counter
          </button>
          <button 
            class="dropdown-item" 
            :class="{ active: activeView === 'two' }"
            @click="setActiveView('two')"
          >
            Directive
          </button>
          <button 
            class="dropdown-item" 
            :class="{ active: activeView === 'three' }"
            @click="setActiveView('three')"
          >
            Both
          </button>
          <div class="dropdown-divider"></div>
          <button 
            class="dropdown-item" 
            :class="{ active: activeView === 'pageOne' }"
            @click="setActiveView('pageOne')"
          >
            List Rendering​

          </button>
          <button 
            class="dropdown-item" 
            :class="{ active: activeView === 'pageTwo' }"
            @click="setActiveView('pageTwo')"
          >
            Event Handling
          </button>
          <button 
            class="dropdown-item" 
            :class="{ active: activeView === 'pageThree' }"
            @click="setActiveView('pageThree')"
          >
            Page Three
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  background: #1f2937;
  border-bottom: 1px solid #374151;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.3);
}

.header-container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.brand {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.logo {
  width: 32px;
  height: 32px;
  border-radius: 6px;
}

.brand-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: #f9fafb;
  letter-spacing: -0.025em;
}

.nav {
  display: flex;
  gap: 2rem;
  align-items: center;
}

.nav-link {
  color: #9ca3af;
  text-decoration: none;
  font-size: 0.9375rem;
  font-weight: 500;
  transition: color 0.2s;
}

.nav-link:hover {
  color: #f9fafb;
}

.dropdown {
  position: relative;
}

.dropdown-toggle {
  background: #374151;
  color: #f9fafb;
  border: 1px solid #4b5563;
  padding: 0.5rem 1rem;
  border-radius: 6px;
  font-size: 0.875rem;
  font-weight: 500;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  transition: all 0.2s;
  min-width: 140px;
  justify-content: space-between;
}

.dropdown-toggle:hover {
  background: #4b5563;
  border-color: #6b7280;
}

.arrow {
  font-size: 0.75rem;
  transition: transform 0.2s;
}

.arrow.open {
  transform: rotate(180deg);
}

.dropdown-menu {
  position: absolute;
  right: 0;
  top: calc(100% + 0.5rem);
  background: #374151;
  border: 1px solid #4b5563;
  border-radius: 8px;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.5), 0 4px 6px -2px rgba(0, 0, 0, 0.3);
  min-width: 140px;
  z-index: 50;
  animation: fadeIn 0.15s ease;
}

.dropdown-item {
  background: none;
  border: none;
  width: 100%;
  padding: 0.625rem 1rem;
  text-align: left;
  color: #e5e7eb;
  font-size: 0.875rem;
  font-weight: 500;
  cursor: pointer;
  transition: background 0.15s;
}

.dropdown-item:first-child {
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
}

.dropdown-item:last-child {
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
}

.dropdown-item:hover {
  background: #4b5563;
}

.dropdown-item.active {
  background: #3b82f6;
  color: #fff;
}

.dropdown-divider {
  height: 1px;
  background: #4b5563;
  margin: 0.25rem 0;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-8px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
