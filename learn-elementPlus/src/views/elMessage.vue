<template>
  <el-button @click="openMsg">消息</el-button>
  <el-button @click="openConfirm">确认框</el-button>
  <el-button @click="openNotifiy">通知</el-button>
  <el-button @click="openNotifiy2">通知2</el-button>
</template>

<script setup lang="ts">
import { ElMessage, ElMessageBox, ElNotification } from 'element-plus'

// 消息
const openMsg = () => {
  ElMessage({
    type: 'success', // success | warning | info | error
    message: '17xueweb.com',
    showClose: true
  })
}

// 确认框
const openConfirm = () => {
  ElMessageBox.confirm('确认删除?', '标题', {
    type: 'warning',
    confirmButtonText: '确认',
    cancelButtonText: '取消'
  })
    .then(() => {
      console.log('确认')
    })
    .catch(() => {
      console.log('取消')
    })
}

// 通知
const openNotifiy = () => {
  ElNotification({
    title: '标题',
    message: '一起学web',
    duration: 1500 // 展示时间 [单位:毫秒]
  })
}

// 通知2
const openNotifiy2 = () => {
  ElNotification({
    type: 'success', // success | warning | info | error
    title: '标题',
    message: '17xueweb.com',
    duration: 1500,
    position: 'bottom-right'
  })
}
</script>
