<script setup lang="ts">
import { ref } from "vue";

var textarea = ref("");

const selectedValue = ref(0);
selectedValue.value = 0;
const options = [
    {
        value: 0,
        label: "前后空格",
    },
    {
        value: 1,
        label: "所有空格",
    },
    {
        value: 2,
        label: "\\t",
    },
];
function RemoveCharacter(character: String) {
    textarea.value = textarea.value.replaceAll(character, "").trim();
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
        <p>请选择移除的字符</p>
        <el-select
            v-model="selectedValue"
            placeholder="前后空格"
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
        <el-button type="primary" @click="CharacterRemove">移除</el-button>
    </el-row>
</template>
