<script setup>
import { defineProps, ref } from 'vue'

const props = defineProps({
  section: {
    type: Number,
    default: 0
  }
})

const title = 'Conditional Redering'
const awesome = ref(true)

// function here
function toggle() {
  awesome.value = !awesome.value
}

</script>

<template>
  <h2>{{ section }} - {{ title }}</h2>
  <button @click="toggle">Toggle</button>
  <h3 v-if="awesome">Vue is awesome</h3>
  <h3 v-else>Oh no 😢</h3>
</template>
