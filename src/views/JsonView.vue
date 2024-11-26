<script setup lang="ts">
import { ref } from 'vue'

var textarea = ref('')

const selectedValue = ref(0)
selectedValue.value = 2
const options = [
  {
    value: 2,
    label: '2',
  },
  {
    value: 4,
    label: '4',
  }
]
function jsonFormat() {
  console.log(selectedValue.value)
  if (selectedValue.value == 0) {
    alert('Please select a value')
  } else {
    textarea.value = "\n" + JSON.stringify(JSON.parse(textarea.value), null, selectedValue.value)

  }
}
</script>


<template>

  <el-row>
    <p>缩进位数</p>
      <el-select
      v-model="selectedValue"
      placeholder="2"
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
      :autosize="{ minRows: 10}"
      type="textarea"
      placeholder="Please input"
      />
    </el-col>
    <el-col :span="12">
      <pre>
        {{ textarea }}
      </pre>
      
    </el-col>
  </el-row>
  <el-row>
    <el-button type="primary" @click="jsonFormat">Format</el-button>
  </el-row> 
</template>
