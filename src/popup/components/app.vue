<template>
  <div class="wrapper">
    <el-button type="danger" @click="test">测试按钮</el-button>
  </div>
</template>
<script setup lang="ts">
  import { ref } from 'vue';
  const a = ref('');
  const test = () => {
    chrome.tabs.getSelected(0, function (tab) {
      chrome.tabs.sendRequest(tab.id || 0, { popAction: 'Test' });
    });
  };
</script>
<style scoped>
  .wrapper {
    width: 100px;
    height: 100px;
    background-color: rgb(248, 214, 242);
  }
</style>
