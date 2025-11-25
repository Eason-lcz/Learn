<template>
  <el-menu
      :default-active="activeIndex"
      class="el-menu-demo"
      mode="horizontal"
      :ellipsis="false"
      @select="handleSelect"
  >
    <div class="topbar-logo-container">
      <img
        class="topbar-logo"
        src="../../../assets/images/miHoYo_Game.png"
        alt="Element logo"
    />
    </div>
    <el-menu-item index="0">Home</el-menu-item>
    <el-menu-item index="1">About</el-menu-item>

    <div class="user-info-container">
      <el-dropdown @command="handleCommand" trigger="click" class="user-dropdown">
        <span class="user-info">
          <el-avatar size="medium" v-if="!isLoggedIn" />
          <el-avatar size="medium" v-else>
            {{ userInfo.username.charAt(0).toUpperCase() }}
          </el-avatar>
          <span v-if="isLoggedIn" class="username">{{ userInfo.username }}</span>
          <i class="el-icon-arrow-down el-icon--right"></i>
        </span>
        <template #dropdown>
          <el-dropdown-menu>
            <el-dropdown-item v-if="!isLoggedIn" command="login">登录</el-dropdown-item>
            <el-dropdown-item v-if="isLoggedIn" command="profile">个人信息</el-dropdown-item>
            <el-dropdown-item v-if="isLoggedIn" command="settings">设置</el-dropdown-item>
            <el-dropdown-item v-if="isLoggedIn" divided command="logout">注销</el-dropdown-item>
          </el-dropdown-menu>
        </template>
      </el-dropdown>
    </div>
  </el-menu>
</template>

<script setup>
import {ref} from 'vue'

const activeIndex = ref('1')
const handleSelect = (key, keyPath) => {
  console.log(key, keyPath)
}

// 处理用户操作命令
const handleCommand = (command) => {
  switch (command) {
    case 'login':
      // 模拟登录
      isLoggedIn.value = true
      userInfo.username = 'admin'
      console.log('用户登录')
      break
    case 'profile':
      console.log('查看个人信息')
      break
    case 'settings':
      console.log('修改设置')
      break
    case 'logout':
      // 模拟注销
      isLoggedIn.value = false
      userInfo.username = ''
      console.log('用户注销')
      break
    default:
      break
  }
}
</script>

<style scoped>

.el-menu--horizontal > .el-menu-item:nth-child(1) {
  margin-right: auto;
}

.topbar-logo-container {
  padding-right: 100px;
}

.topbar-logo {
  width: 50px;
}

.user-info-container {
  margin-left: auto; /* 使元素靠右 */
  padding: 20px;
}
.user-dropdown {
  top: calc(50% - 20px);
}

.user-info {
  display: flex;
  align-items: center;
  cursor: pointer;
  color: #606266;
}

.username {
  margin: 0 10px;
}
</style>
