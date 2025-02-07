<script setup>
  import { defineProps, ref, computed } from 'vue'

  const props = defineProps({
    section: {
      type: Number,
      default: 0
    }
  })

  let id = 0
  const newTodo = ref('')
  const hideCompleted = ref(false)
  const todos = ref([
    { id: id++, text: 'Learn HTML', done: true },
    { id: id++, text: 'Learn javascript', done: true },
    { id: id++, text: 'Learn Vue', done: false },

  ])

  const title = ref('Computed property')

  function addTodo() {
    todos.value.push({ id: id++, text: newTodo, done: false })
  }

  function deleteTodo(todo) {
    todos.value = todos.value.filter((t) => t.id !== todo.id)
  }

  const filteredTodos = computed(() => {
    return hideCompleted.value ? todos.value.filter((t) => !t.done) : todos.value
  })

</script>

<template>
  <h2> {{ section }} - {{ title }} </h2>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" placeholder="Type here ..." >
    <button>Add todo</button>
  </form>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="deleteTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="hideCompleted = !hideCompleted">{{ hideCompleted ? 'Show all' : 'Hide todos' }}</button>
</template>
<style>
  .done {
    text-decoration: line-through ;
  }
</style>
