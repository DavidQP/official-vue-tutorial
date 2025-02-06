<script setup>
import { defineProps, ref } from 'vue'

const props = defineProps({
  section: {
    type: Number,
    default: 0
  }
})

const title = ref('List Rendering')
let id = 0
const newTodo = ref('')
const todos = ref([
  { id: id++, text: 'Learn HTML' },
  { id: id++, text: 'Learn Javascript'},
  { id: id++, text: 'Learn Vue' }
])

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value })
  newTodo.value = ''
}

function removeTodo(currentTodo) {
  todos.value = todos.value.filter((todo) => todo.id !== currentTodo.id)
}

</script>

<template>
  <h2>{{ section }} - {{ title }}</h2>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" placeholder="Type your new todo here.">
    <button type="submit">Add todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>
