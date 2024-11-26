<script setup lang="ts">
// 导入TheWelcome组件
import TheWelcome from '../components/TheWelcome.vue'
</script>

<template>
  <main>
    <!-- 卡片组件 -->
    <el-card style="max-width: 200px;">
      <!-- 按钮组件，最大宽度为200px -->
      <RouterLink to="/json">JSON 格式化</RouterLink>

    </el-card>

        <!-- 卡片组件 -->
    <el-card style="max-width: 200px;">
      <!-- 按钮组件，最大宽度为200px -->
      <RouterLink to="/UrlTransform">Url编码/解码</RouterLink>
    </el-card>
    <!-- <TheWelcome /> -->
  </main>
</template>
