<script setup lang="ts">
import { ref } from "vue";

const textarea = ref("");

const selectedValue = ref(0);
selectedValue.value = 0;
const options = [
    {
        value: 0,
        label: "front-end space(前后空格)",
    },
    {
        value: 1,
        label: "all space(所有空格)",
    },
    {
        value: 2,
        label: "\\t",
    },
];
function RemoveCharacter(character = "") {
    textarea.value = textarea.value
        .replace(new RegExp(character, "gi"), "")
        .trim();
}

function CharacterRemove() {
    if (selectedValue.value == 0) {
        textarea.value = "\n" + textarea.value.trim();
    } else if (selectedValue.value == 1) {
        RemoveCharacter(" ");
        textarea.value = "\n" + textarea.value;
    } else if (selectedValue.value == 2) {
        RemoveCharacter("\t");
        textarea.value = "\n" + textarea.value;
    }
}
</script>

<template>
    <el-row>
        <p>Please select(请选择移除的字符)</p>
        <el-select
            v-model="selectedValue"
            placeholder="front-end space(前后空格)"
            size="large"
            style="width: 240px"
        >
            <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value"
            />
        </el-select>
    </el-row>
    <el-row>
        <el-col :span="12">
            <el-input
                v-model="textarea"
                style="width: 100%"
                :rows="10"
                :autosize="{ minRows: 10 }"
                type="textarea"
                placeholder="Please input"
            />
        </el-col>
        <el-col :span="12">
            <pre>
        {{ textarea }}
      </pre
            >
        </el-col>
    </el-row>
    <el-row>
        <el-button type="primary" @click="CharacterRemove">Remove Space(移除空格)</el-button>
    </el-row>
</template>
