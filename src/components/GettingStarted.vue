<script setup>
import { ref } from 'vue'

const message = ref(`Welcome from ${Intl.DateTimeFormat().resolvedOptions().timeZone.split('/').pop()}`)
</script>

<template>
  <h2>{{ message }}</h2>
</template>
