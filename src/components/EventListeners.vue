<script setup>
import { defineProps, ref } from 'vue'

const props = defineProps({
  section: {
    type: Number,
    default: 0
  }
})

const title = ref('Event Listeners')
const count = ref(0)

// functions
function increment() {
  count.value++;
}

</script>

<template>
  <h2>{{ section }} - {{ title }}</h2>
  <button @click="increment">Count is : {{ count }}</button>
</template>
