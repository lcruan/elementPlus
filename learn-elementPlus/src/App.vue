<script setup lang="ts">
import { ref } from 'vue'
const tabPosition = ref('left')

import elButton from '@/views/elButton.vue'
import elIcon from '@/views/elIcon.vue'
</script>

<template>
  <el-tabs :tab-position="tabPosition" style="height: 100%" class="demo-tabs">
    <el-tab-pane label="按钮">
      <elButton></elButton>
    </el-tab-pane>
    <el-tab-pane label="图标">
      <elIcon></elIcon>
    </el-tab-pane>
    <el-tab-pane label="Role">Role</el-tab-pane>
    <el-tab-pane label="Task">Task</el-tab-pane>
  </el-tabs>
</template>

<style scoped></style>
