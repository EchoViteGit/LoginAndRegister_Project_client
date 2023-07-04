<script setup>
import {User} from '@element-plus/icons-vue'
import {Lock} from '@element-plus/icons-vue'
</script>

<template>
  <div style="width: 100vw; height: 100vh; overflow: hidden; display: flex">
    <div style="flex: 1">
        <el-image
          style="width: 100%; height: 100%" fit="cover"
        src="https://img.zcool.cn/community/01c8f15aeac135a801207fa16836ae.jpg@1280w_1l_2o_100sh.jpg" />
    </div>
    <div style="width: 400px; background-color: white">
      <div style="text-align: center;margin:0 20px">
        <div style="margin-top: 150px">
          <div style="font-size: 25px;font-weight: bold">登录</div>
          <div style="font-size: 14px; color: grey;margin-top: 20px">进入系统前请先输入用户名和密码进行登录</div>
        </div>
        <div style="margin-top: 30px">
          <el-input type="text" placeholder="用户名/邮箱" >
            <template #prefix>
              <el-icon><User /></el-icon>
            </template>
          </el-input>
          <el-input type="password" placeholder="密码" style="margin-top: 10px">
            <template #prefix>
              <el-icon><Lock /></el-icon>
            </template>
          </el-input>
        </div>
        <div style="margin-top: 10px;height: 40px">
          <el-row>
            <el-col :span="12" style="text-align: left">
              <el-checkbox v-model="checked" label="记住密码" size="large" />
            </el-col>
            <el-col :span="12" style="text-align: right">
              <el-link style="line-height: 40px;" :underline="false">忘记密码？</el-link>
            </el-col>
          </el-row>
        </div>
        <div style="margin-top: 30px">
          <el-button type="success" style="width: 270px" plain>登录</el-button>
        </div>
        <el-divider>
          <span style="color: gray;align-items: center" >没有账号</span>
        </el-divider>
        <div>
          <el-button type="warning" style="width: 270px" plain>注册账号</el-button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
