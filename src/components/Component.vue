<script setup>
  import { defineProps, onMounted, ref } from 'vue'

  const props = defineProps({
    section: {
      type: Number,
      default: 0
    }
  })

  const titleElementRef = ref('No title')
  const title = ref('Components')

  onMounted(() => {
    titleElementRef.value.textContent = `${props.section} - ${title.value}`
  })
</script>
<template>
  <h2 ref="titleElementRef"></h2>
  <h3>A child Component</h3>
</template>
