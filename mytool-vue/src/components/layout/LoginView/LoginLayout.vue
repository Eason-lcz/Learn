<template>
  <div class="login-layout">
    <el-row :gutter="20" align="middle" class="login-layout-row">
      <el-col :span="18">
        <div class="grid-content ep-bg-purple"/>
      </el-col>
      <el-col :span="6">
        <div class="grid-content ep-bg-purple"/>
        <Login></Login>
      </el-col>
    </el-row>
  </div>
</template>

<script setup>
import Login from '../../../views/Login/Login.vue'
</script>

<style scoped>
.login-layout {
  height: 100vh;
  width: 100vw;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.login-layout-row {
  height: 100%;
}

.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
</style>