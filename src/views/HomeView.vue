<script setup lang="ts">
// 导入TheWelcome组件
import TheWelcome from "../components/TheWelcome.vue";
</script>

<template>
    <main>
        <!-- 卡片组件 -->
        <el-card style="max-width: 200px">
            <!-- 按钮组件，最大宽度为200px -->
            <RouterLink to="/json">JSON format(格式化)</RouterLink>
        </el-card>

        <!-- 卡片组件 -->
        <el-card style="max-width: 200px">
            <!-- 按钮组件，最大宽度为200px -->
            <RouterLink to="/UrlTransform">Url encode/decode(编码/解码)</RouterLink>
        </el-card>
        <!-- 卡片组件 -->
        <el-card style="max-width: 200px">
            <!-- 按钮组件，最大宽度为200px -->
            <RouterLink to="/CharacterRemove">Remove unused characters(移除多余字符)</RouterLink>
        </el-card>

        <!-- <TheWelcome /> -->
    </main>
</template>
