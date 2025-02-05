<script setup>
import { reactive, ref } from 'vue'

const props = defineProps({
  section: {
    type: Number,
    default: 0
  }
})
const title = ref('Declarative Redering');
const counter = reactive({
  count: 0
})
</script>

<template>
  <h2>{{ section }} - {{ title }}</h2>
  <p>Count is: {{ counter.count }}</p>
</template>
