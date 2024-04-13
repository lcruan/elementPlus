<script setup lang="ts">
import { ref } from 'vue'
const tabPosition = ref('left')
const tabsData = [
  {
    label: '按钮',
    com: elButton
  },
  {
    label: '图标',
    com: elIcon
  },
  {
    label: '消息框',
    com: elMessage
  },
  {
    label: '菜单',
    com: elMenu
  },
  // {
  //   label: '标签页',
  //   com: elTabs
  // }
]
import elButton from '@/views/elButton.vue'
import elIcon from '@/views/elIcon.vue'
import elMessage from '@/views/elMessage.vue'
import elMenu from '@/views/elMenu.vue'
// import elTabs from '@/views/elTabs.vue'
</script>

<template>
  <el-tabs :tab-position="tabPosition" style="height: 100%" class="demo-tabs">
    <el-tab-pane v-for="(item, index) in tabsData" :key="index" :label="item.label">
      <component :is="item.com"></component>
    </el-tab-pane>
  </el-tabs>
</template>

<style scoped></style>
