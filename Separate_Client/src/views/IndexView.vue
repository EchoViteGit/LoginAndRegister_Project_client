<script setup>
import { get } from "@/net";
import { ElMessage } from "element-plus";
import router from "@/router";

const logout = () => {
  get('/api/auth/logout',(message)=>{
    ElMessage.success(message)
    router.push('/')
  })
}
</script>

<template>
  <div>欢迎进入系统</div>
  <div>
    <el-button @click="logout" type="danger" plain>
      退出登录
    </el-button>
  </div>
</template>

<style scoped>

</style>
