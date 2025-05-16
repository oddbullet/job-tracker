<template>
  <div>
    <h1>{{ message }}</h1>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const message = ref('Loading...')

onMounted(async () => {
  const res = await fetch('/api/hello')
  const data = await res.json()
  message.value = data.message
})
</script>
