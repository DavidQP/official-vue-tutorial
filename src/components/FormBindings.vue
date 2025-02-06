<script setup>
  import { defineProps, ref } from 'vue'

  const props = defineProps({
    section: {
      type: Number,
      default: 0
    }
  })

  const title = ref('Form Bindings')
  const textBefore = ref('')
  const textAfter = ref('')

  // functins here

  function onInput(event) {
    textBefore.value = event.target.value
  }
</script>

<template>
  <h2>{{ section }} - {{ title }}</h2>
  <input :value="textBefore" @input="onInput" placeholder="type here">
  <p>{{ textBefore }}</p>
  <!-- A simple shortcut for v-bind and v-on:input  -->
  <input v-model="textAfter"></input>
  <p>{{ textAfter }}</p>
</template>
