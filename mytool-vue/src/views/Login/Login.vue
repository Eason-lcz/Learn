<template>
  <div class="card">
    <div class="title">登录</div>
    <Form>
      <el-form-item label="用户名">
        <el-input v-model="username" placeholder="请输入用户名"/>
      </el-form-item>
      <el-form-item label="密&emsp;码">
        <el-input v-model="password" type="password" placeholder="请输入密码" show-password/>
      </el-form-item>
      <el-form-item>
        <VerificationCode></VerificationCode>
      </el-form-item>
      <el-form-item class="submit-btn">
        <el-button type="primary" style="width: 100px">登录</el-button>
      </el-form-item>
    </Form>
    <div class="coagent">
      <ul>
        <li>
          <a href="">忘记密码？</a>
        </li>
        <span>|</span>
        <li>
          <a href="">注册账号</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue'
import VerificationCode from "../../components/common/VerificationCode/VerificationCode.vue"

const username = ref('')
const password = ref('')

</script>


<style scoped>
.title {
  font-size: 20px;
  font-weight: bold;
  color: #000;
  text-align: center;
  padding: 20px 0;
}

.card {
  width: 300px;
  margin: 0;
  border: 1px solid #ffffff;
  padding: 20px;
  background-color: rgba(255, 255, 255, 0.8);
  border-radius: 10px;
  box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.2);
}

.submit-btn {
  text-align: center;
  margin: 20px auto;
  padding-bottom: 20px;
  padding-left: calc(50% - 50px);
}
.coagent {
  text-align: center;
  margin: 20px auto;
  padding-bottom: 20px;
  padding-left: calc(50% - 50px);
  line-height: 40px;
}
ul {
  list-style: none;
  display: flex;  /* 添加flex布局 */
  align-items: center;  /* 垂直居中对齐 */
  justify-content: center;  /* 水平居中对齐 */
  margin: 0;
  padding: 0;
}

li {
  display: list-item;
  unicode-bidi: isolate;
  width: auto;  /* 宽度自适应 */
  margin: 0 10px;  /* 调整间距 */
}

span {
  color: #c0c4cc;
}
</style>