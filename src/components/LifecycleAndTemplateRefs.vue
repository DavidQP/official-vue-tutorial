<script setup>
  import { defineProps, onMounted, ref } from 'vue'

  const props = defineProps({
    section: {
      type: Number,
      default: 0
    }
  })

  const title = ref('Lifecycle and template refs')
  const pElementRef = ref(null)

  // functions
  onMounted(() => {
    pElementRef.value.textContent = 'On mount executed.'
  })
</script>

<template>
  <h2>{{ section }} - {{ title }} </h2>
  <p ref="pElementRef"> Hello </p>
</template>
