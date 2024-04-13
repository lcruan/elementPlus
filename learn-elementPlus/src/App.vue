<script setup lang="ts">
import { ref } from 'vue'
const tabPosition = ref('left')

import elButton from '@/views/elButton.vue'
import elIcon from '@/views/elIcon.vue'
import elMessage from '@/views/elMessage.vue'
import elMenu from '@/views/elMenu.vue'
</script>

<template>
  <el-tabs :tab-position="tabPosition" style="height: 100%" class="demo-tabs">
    <el-tab-pane label="按钮">
      <elButton></elButton>
    </el-tab-pane>
    <el-tab-pane label="图标">
      <elIcon></elIcon>
    </el-tab-pane>
    <el-tab-pane label="消息框"><elMessage/></el-tab-pane>
    <el-tab-pane label="菜单"><elMenu/></el-tab-pane>
  </el-tabs>
</template>

<style scoped></style>
