<script setup>
import { defineProps, onMounted, ref, watch } from 'vue'

const props = defineProps({
  section: {
    type: Number,
    default: 0
  }
})

const titleElement = ref(null)
const title = ref('Watchers')
const todoId = ref(1)
const todoData = ref(null)


onMounted(() => {
  titleElement.value.textContent = `${props.section} - ${title}`
})

async function fetchedData() {
  todoData.value = null
  const response = await fetch(`https://jsonplaceholder.typicode.com/todos/${todoId.value}`)
  todoData.value = await response.json()
}

fetchedData()
watch(todoId, fetchedData)
</script>

<template>
  <h2 ref="titleElement">{{ section }} - {{ title }}</h2>
  <h3>todoId: {{ todoId }}</h3>
  <button @click="todoId++">Fetch next Id</button>
  <p v-if="!todoData">Loading ...</p>
  <pre>{{ todoData }}</pre>
</template>
