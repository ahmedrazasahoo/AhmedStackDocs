<template>
  <aside :class="['sidebar', { collapsed: isCollapsed }]">
    <!-- Sidebar Header -->
    <div class="sidebar-header">
      <div class="header-left" v-if="!isCollapsed">
        <h2 class="menu-title">📚 Docs Menu</h2>
      </div>

      <div class="header-right">
        <button class="toggle-btn" @click="toggleSidebar">
          {{ isCollapsed ? '→' : '←' }}
        </button>

        
      </div>
    </div>

    <!-- Sidebar Menu -->
    <nav class="sidebar-nav">
      <ul>
        <li v-for="item in menuItems" :key="item.name">
          <button class="nav-item" @click="handleClick(item.name)">
            <span class="icon">{{ item.icon }}</span>
            <span v-if="!isCollapsed" class="label">{{ item.name }}</span>
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
  width: 260px;
  background: linear-gradient(135deg, #16a34a, #22c55e);
  color: white;
  height: 100vh;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  transition: all 0.3s ease;
  border-top-right-radius: 1rem;
  border-bottom-right-radius: 1rem;
  box-shadow: 3px 0 10px rgba(0, 0, 0, 0.15);
  overflow: hidden;
}

.sidebar.collapsed {
  width: 90px;
}

.sidebar-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 1.5rem;
}

.menu-title {
  font-size: 1.2rem;
  font-weight: bold;
  letter-spacing: 0.5px;
}

.header-right {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.toggle-btn,
.count-btn {
  background: rgba(255, 255, 255, 0.15);
  border: none;
  color: white;
  padding: 0.4rem 0.7rem;
  border-radius: 0.5rem;
  cursor: pointer;
  transition: all 0.2s ease;
}

.toggle-btn:hover,
.count-btn:hover {
  background: rgba(255, 255, 255, 0.25);
  transform: scale(1.05);
}

/* Nav Menu */
.sidebar-nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-item {
  width: 100%;
  background: transparent;
  color: white;
  border: none;
  text-align: left;
  display: flex;
  align-items: center;
  gap: 0.8rem;
  padding: 0.8rem 1rem;
  border-radius: 0.6rem;
  cursor: pointer;
  transition: all 0.2s ease;
}

.nav-item:hover {
  background: rgba(255, 255, 255, 0.15);
  transform: translateX(3px);
}

.icon {
  font-size: 1.3rem;
}

.label {
  font-weight: 500;
  font-size: 1rem;
}

/* Responsive */
@media (max-width: 768px) {
  .sidebar {
    position: fixed;
    height: 100vh;
    z-index: 1000;
  }
}
</style>
