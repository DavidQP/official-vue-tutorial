<script setup>
import { ref } from 'vue'
const props = defineProps({
  section: {
    type: Number,
    default: 0
  }
})
const title = ref('Getting stated');
const message = ref(`Welcome from ${Intl.DateTimeFormat().resolvedOptions().timeZone.split('/').pop()}`)
console.log(props.section);
</script>

<template>
  <h2>{{ section }} - {{ title }}</h2>
  <p>{{ message }}</p>
</template>
