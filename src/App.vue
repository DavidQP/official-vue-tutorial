
<script setup>
import { ref } from 'vue';
import GettingStarted from '@/components/GettingStarted.vue'
import DeclarativeRendering from '@/components/DeclarativeRendering.vue'
import AttributesBinding from '@/components/AttributesBinding.vue'
const section = ref(0);
</script>

<template>
  <h1>Vue official tutorial</h1>
  <GettingStarted :section="1" />
  <DeclarativeRendering :section="2" />
  <AttributesBinding :section="3" />
</template>
