---
layout: page
---

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  window.location.href = '/en/docs/'
})
</script>

<div style="display: flex; justify-content: center; align-items: center; height: 50vh; flex-direction: column;">
  <p>Redirecting to documentation...</p>
  <p style="margin-top: 20px;">
    <a href="/en/docs/">Click here if not redirected</a>
  </p>
</div>
