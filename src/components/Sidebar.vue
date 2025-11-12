<template>
  <aside :class="['sidebar', { collapsed: isCollapsed }]">
    <div class="sidebar-header">
      <h2 v-if="!isCollapsed" class="sidebar-title">Docs Menu</h2>
      <button class="toggle-btn" @click="toggleSidebar" :title="isCollapsed ? 'Expand' : 'Collapse'">
        {{ isCollapsed ? '→' : '←' }}
      </button>
    </div>

    <nav class="sidebar-nav">
      <ul class="nav-list">
        <li v-for="item in menuItems" :key="item.name">
          <button class="nav-item" @click="handleClick(item.name)">
            <span class="nav-icon">{{ item.icon }}</span>
            <span v-if="!isCollapsed" class="nav-label">{{ item.name }}</span>
          </button>
        </li>
      </ul>
    </nav>
  </aside>
</template>

<script setup>
import { ref } from "vue";


const isCollapsed = ref(false);

const toggleSidebar = () => {
  isCollapsed.value = !isCollapsed.value;
};

const handleClick = (name) => {
  alert(`You clicked on: ${name}`);
};

const menuItems = [
  { name: "Home", icon: "🏠" },
  { name: "Guides", icon: "📘" },
  { name: "Components", icon: "🧩" },
  { name: "Settings", icon: "⚙️" },
];
</script>

<style scoped>
.sidebar {
  width: 240px;
  background: #1f2937;
  border-right: 1px solid #374151;
  display: flex;
  flex-direction: column;
  transition: width 0.3s ease;
  overflow: hidden;
}

.sidebar.collapsed {
  width: 64px;
}

.sidebar-header {
  padding: 1.5rem 1rem;
  border-bottom: 1px solid #374151;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.sidebar-title {
  font-size: 0.875rem;
  font-weight: 600;
  color: #f9fafb;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.toggle-btn {
  background: #374151;
  border: 1px solid #4b5563;
  color: #9ca3af;
  width: 28px;
  height: 28px;
  border-radius: 6px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.875rem;
  transition: all 0.2s;
}

.toggle-btn:hover {
  background: #4b5563;
  color: #f9fafb;
}

.sidebar-nav {
  padding: 1rem;
  flex: 1;
  overflow-y: auto;
}

.nav-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.nav-item {
  width: 100%;
  background: transparent;
  border: none;
  text-align: left;
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.625rem 0.75rem;
  border-radius: 6px;
  cursor: pointer;
  color: #9ca3af;
  font-size: 0.875rem;
  font-weight: 500;
  transition: all 0.15s;
}

.nav-item:hover {
  background: #374151;
  color: #f9fafb;
}

.nav-icon {
  font-size: 1.125rem;
  flex-shrink: 0;
}

.nav-label {
  white-space: nowrap;
}

@media (max-width: 768px) {
  .sidebar {
    position: fixed;
    height: 100vh;
    z-index: 40;
  }
}
</style>
