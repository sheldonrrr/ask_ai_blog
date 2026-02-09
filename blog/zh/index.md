---
layout: page
---

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  window.location.href = '/zh/docs/'
})
</script>

<div style="display: flex; justify-content: center; align-items: center; height: 50vh; flex-direction: column;">
  <p>正在跳转到文档...</p>
  <p style="margin-top: 20px;">
    <a href="/zh/docs/">如果没有自动跳转，请点击这里</a>
  </p>
</div>
