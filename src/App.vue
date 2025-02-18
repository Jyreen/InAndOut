<template>
  <div class="app-container">
    <header class="sidebar">
      <el-menu
        active-text-color="#1f8e7e"
        background-color="#fff"
        class="el-menu-vertical-demo"
        default-active="1"
        text-color="#000000"
        @open="handleOpen"
        @close="handleClose"
        style="height: 100vh; width: 220px"
      >
        <el-menu-item class="no-hover">
          <img src="../src/assets/skanlog.png" alt="skanlog" height="40" width="150" />
        </el-menu-item>
        <RouterLink to="/home">
          <el-menu-item index="1">
            <template #title>
              <el-icon><HomeFilled /></el-icon>
              <span>Home</span>
            </template>
          </el-menu-item>
        </RouterLink>
        <RouterLink to="/shipments">
          <el-menu-item index="2">
            <template #title>
              <el-icon><Box /></el-icon>
              <span>Shipments</span>
            </template>
          </el-menu-item>
        </RouterLink>
        <RouterLink to="/employees">
          <el-menu-item index="3">
            <template #title>
              <el-icon><User /></el-icon>
              <span>Employees</span>
            </template>
          </el-menu-item>
        </RouterLink>
        <RouterLink to="/activitylogs">
          <el-menu-item index="4">
            <el-icon><Tickets /></el-icon>
            <span>Activity Logs</span>
          </el-menu-item>
        </RouterLink>
      </el-menu>
    </header>

    <header class="top-header">
      <h2>Warehouse No. 4</h2>
      <span class="user-greeting">Hi, Admin!</span>
    </header>

    <main class="main-content">
      <RouterView />
    </main>
  </div>
</template>

<script>
import { ref } from 'vue'
import { User, Box, Tickets, HomeFilled } from '@element-plus/icons-vue'

export default {
  components: {    User,
    Box,
    Tickets,
    HomeFilled,
  },
  setup() {
    const isCollapse = ref(true)

    const handleOpen = (key, keyPath) => {
      console.log(key, keyPath)
    }

    const handleClose = (key, keyPath) => {
      console.log(key, keyPath)
    }

    return {
      isCollapse,
      handleOpen,
      handleClose,
    }
  },
}
</script>

<style scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
.no-hover {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80px; 
  pointer-events: none;
}

.no-hover img {
  display: block;
  max-width: 100%;
  height: auto;
}
.el-menu {
  border-radius: 20px; 
  overflow: hidden;
}

.el-menu-item {
  border-radius: 10px; 
  margin: 5px;
}
</style>
