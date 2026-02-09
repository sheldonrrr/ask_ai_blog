---
layout: page
---

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  const lang = navigator.language || navigator.userLanguage
  if (lang.startsWith('zh')) {
    window.location.href = '/zh/docs/'
  } else {
    window.location.href = '/en/docs/'
  }
})
</script>

<div style="display: flex; justify-content: center; align-items: center; height: 50vh; flex-direction: column;">
  <p>Redirecting...</p>
  <p style="margin-top: 20px;">
    <a href="/en/docs/">English</a> | <a href="/zh/docs/">中文</a>
  </p>
</div>
