<script setup lang="ts">
// 导入TheWelcome组件
import TheWelcome from '../components/TheWelcome.vue'
</script>

<template>
  <main>
    <!-- 卡片组件 -->
    <el-card>
      <!-- 按钮组件，最大宽度为200px -->
      <RouterLink to="/json">JSON 格式化</RouterLink>
      <!-- <el-button style="max-width: 200px;"  >JSON 格式化</el-button> -->
    </el-card>
    <!-- <TheWelcome /> -->
  </main>
</template>
