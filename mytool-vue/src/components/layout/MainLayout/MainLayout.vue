<template>
  <div class="common-layout">
    <el-container>
      <el-header>
        <TopBar></TopBar>
      </el-header>
      <el-container>
        <el-aside width="200px">
          <SideBar></SideBar>
        </el-aside>
        <el-main>
          <router-view></router-view>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script setup>
import TopBar from "../../common/Bar/TopBar.vue";
import SideBar from "../../common/Bar/SideBar.vue";

</script>

<style scoped>

</style>