<template>
    <el-menu
        :default-active="activeIndex"
        class="el-menu-demo"
        mode="horizontal"
        :ellipsis="false"
        @select="handleSelect"
    >
        <el-menu-item index="0">
            <RouterLink to="/"
                ><img
                    style="width: 100px; height: 65px"
                    src="@/assets/favicon.svg"
                    alt="Element logo"
            /></RouterLink>
        </el-menu-item>

        <el-menu-item index="1">
            <RouterLink to="/json">JSON Format(格式化)</RouterLink>
        </el-menu-item>
        <el-menu-item index="4">
            <RouterLink to="/UrlTransform">Url Encode/De(编码/解码)</RouterLink>
        </el-menu-item>
        <el-menu-item index="5">
            <RouterLink to="/CharacterRemove">Remove characters(移除多余字符)</RouterLink>
        </el-menu-item>
        <el-menu-item index="3">
            <RouterLink to="/about">About</RouterLink>
        </el-menu-item>
        <el-sub-menu index="2">
            <template #title>Workspace</template>
            <el-menu-item index="2-1">item one</el-menu-item>
            <el-menu-item index="2-2">item two</el-menu-item>
            <el-menu-item index="2-3">item three</el-menu-item>
            <el-sub-menu index="2-4">
                <template #title>item four</template>
                <el-menu-item index="2-4-1">item one</el-menu-item>
                <el-menu-item index="2-4-2">item two</el-menu-item>
                <el-menu-item index="2-4-3">item three</el-menu-item>
            </el-sub-menu>
        </el-sub-menu>
    </el-menu>
</template>

<script lang="ts" setup>
import { ref } from "vue";

const activeIndex = ref("1");
const handleSelect = (key: string, keyPath: string[]) => {
    console.log(key, keyPath);
};
</script>

<style>
.el-menu--horizontal > .el-menu-item:nth-child(1) {
    margin-right: auto;
}
</style>
