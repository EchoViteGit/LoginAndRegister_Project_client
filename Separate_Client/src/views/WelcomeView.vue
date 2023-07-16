<script setup>
</script>

<template>
  <div style="width: 100vw; height: 100vh; overflow: hidden; display: flex">
    <div style="flex: 1">
      <el-image
        style="width: 100%; height: 100%" fit="cover"
        src="https://img.zcool.cn/community/01c8f15aeac135a801207fa16836ae.jpg@1280w_1l_2o_100sh.jpg" />
    </div>
    <div class="welcome-title">
      <div> SpringBoot3 + SpringSecurity + MyBatis + VUE3 </div>
    </div>
    <div style="width: 400px; background-color: white;z-index: 1">
      <router-view v-slot="{ Component }">
        <transition name="el-fade-in-linear" mode="out-in">
          <component :is="Component" style="height: 100%" />
        </transition>
      </router-view>
    </div>
  </div>
</template>

<style scoped>
  .welcome-title{
      position: absolute;
      bottom: 30px;
      left: 30px;
      color: white;
      font-size: 30px;
      font-weight: bold;
      text-shadow: 0 0 20px black;
      font-family: 华文楷体,serif;
  }
</style>
