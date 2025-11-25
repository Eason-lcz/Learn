<template>
  <el-row gutter="5">
    <el-col :span="18">
      <el-input v-model="vercode" style="height: 40px; margin-right: 10px;" placeholder="请输入验证码"/>
    </el-col>
    <el-col :span="6">
      <el-image src="VerificationCodeUrl" alt="验证码" style="width: 80px; height: 40px; margin-right: 10px;"
                @click=" refreshVerificationCode"
                @error="handleImageError"
                fit="cover"/>
    </el-col>
  </el-row>
</template>

<script setup>
import {ref} from 'vue'

const vercode = ref('')


const VerificationCodeUrl = ref('/vercode.png')

</script>

<style scoped>

</style>