<script setup>
import { onMounted, ref } from 'vue'
const emit  = defineEmits(['response']);
emit('response', 'Hello from child');
const props = defineProps({
  section: {
    type: Number,
    default: 0
  }
})

const title = ref('Emit')
const titleElementRef = ref(null)

// functions
onMounted(() => {
  titleElementRef.value.textContent = `${props.section} - ${title.value}`
})

</script>

<template>
  <h2 ref="titleElementRef"></h2>
</template>
