<script setup>
import { Lock, User } from "@element-plus/icons-vue";
import { reactive } from "vue";
import { ElMessage } from "element-plus";
import { post } from "@/net";
import router from "@/router";

const form = reactive({
  username:'',
  password:'',
  remember:false
})

const login = () => {
  if(!form.username||!form.password){
    ElMessage.warning("请填写用户名和密码")
  }
  else{
    post('/api/auth/login',{
      username:form.username,
      password:form.password,
      remember:form.remember
    },(message)=>{
      ElMessage.success(message)
      router.push('/index')
    })
  }
}
</script>

<template>
  <div style="text-align: center;margin:0 20px">
    <div style="margin-top: 150px">
      <div style="font-size: 35px;font-weight: bold;font-family: 华文楷体">登录</div>
      <div style="font-size: 14px; color: grey;margin-top: 20px">进入系统前请先输入用户名和密码进行登录</div>
    </div>
    <div style="margin-top: 30px">
      <el-input v-model="form.username" type="text" placeholder="用户名/邮箱" >
        <template #prefix>
          <el-icon><User /></el-icon>
        </template>
      </el-input>
      <el-input v-model="form.password" type="password" placeholder="密码" style="margin-top: 10px">
        <template #prefix>
          <el-icon><Lock /></el-icon>
        </template>
      </el-input>
    </div>
    <div style="margin-top: 10px;height: 40px">
      <el-row>
        <el-col :span="12" style="text-align: left">
          <el-checkbox v-model="form.remember" label="记住密码" size="large" />
        </el-col>
        <el-col :span="12" style="text-align: right">
          <el-link style="line-height: 40px;" :underline="false">忘记密码？</el-link>
        </el-col>
      </el-row>
    </div>
    <div style="margin-top: 30px">
      <el-button type="success" style="width: 270px" @click="login" plain>登录</el-button>
    </div>
    <el-divider>
      <span style="color: gray;align-items: center" >没有账号</span>
    </el-divider>
    <div>
      <el-button type="warning" style="width: 270px" @click="router.push('/register')" plain>注册账号</el-button>
    </div>
  </div>
</template>

<style scoped>

</style>
