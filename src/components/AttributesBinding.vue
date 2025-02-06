<script setup>
import { ref } from 'vue';

const props = defineProps({
  section: {
    type: Number,
    default: 0
  }
})

const title = ref('Attributes Binding');
const titleClass = ref('title');
</script>

<template>
  <h2>{{ section }} - {{ title }}</h2>
  <p :class="titleClass">Make me red!</p>
</template>

<style>
.title {
  color: red;
}
</style>
