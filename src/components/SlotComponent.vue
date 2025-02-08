<script setup>
import { ref, onMounted } from 'vue'

const props = defineProps({
  section: {
    type: Number,
    default: 0
  }
})

const title = ref('Slot')
const titleElementRef = ref(null)

// functions

onMounted(() => {
  titleElementRef.value.textContent = `${props.section} - ${title.value}`
})

</script>

<template>
  <h2 ref="titleElementRef"></h2>
  <slot>Fallback content</slot>
</template>
