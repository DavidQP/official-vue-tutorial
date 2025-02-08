<script setup>
import { onMounted, ref } from 'vue';
const props = defineProps({
  section: {
    type: Number,
    default: 0
  },
  msg: {
    type: String,
    default: 'No message'
  }
});

const title = ref('Props');
const titleElementRef = ref(null);
const pElementRef = ref(null);

// function

onMounted(() => {
  titleElementRef.value.textContent =  `${ props.section } - ${title.value}`;
  pElementRef.value.textContent = props.msg;
})

</script>



<template>
  <h2 ref="titleElementRef"></h2>
  <p ref="pElementRef"></p>
</template>
