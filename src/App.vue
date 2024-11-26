<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
import Header from './components/layout/Header.vue'
import 'element-plus/dist/index.css'

</script>
<template>
    <el-container>
      <el-header>
        <Header />
      </el-header>
      <el-main>
        <RouterView />
      </el-main>
      <el-footer>Footer</el-footer>
    </el-container>
</template>

<!-- <template> -->

  <!-- <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header> -->

  <!-- <RouterView /> -->
<!-- </template> -->

<style scoped>

.el-container {
  height: 100%;
}

.el-header,
.el-footer
{
  background-color: #b3c0d1; color: #333; text-align: center; line-height: 60px;
}

.el-aside {
  background-color: #d3dce6; color: #333; text-align: center; line-height: 200px;
}

.el-main {
  background-color: #e9eef3; color: #333; 
}

.el-menu {
  background-color: #d3dce6;
}

</style>
