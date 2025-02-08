
<script setup>
import { ref } from 'vue';
import GettingStarted from '@/components/GettingStarted.vue'
import DeclarativeRendering from '@/components/DeclarativeRendering.vue'
import AttributesBinding from '@/components/AttributesBinding.vue'
import EventListeners  from '@/components/EventListeners.vue'
import FormBindings from '@/components/FormBindings.vue'
import ConditionalRendering from '@/components/ConditionalRendering.vue'
import ListRendering from '@/components/ListRendering.vue'
import ComputedProperty from '@/components/ComputedProperty.vue'
import LifecycleAndTemplateRefs from '@/components/LifecycleAndTemplateRefs.vue'
import Watchers from '@/components/Watchers.vue'
import Component from '@/components/Component.vue'
import Props from '@/components/Props.vue'
import Emit from '@/components/Emit.vue'

const title = ref('Vue Official tutorial')
const section = ref(0);
const greeting = ref('Hello from parent')
// Emit section
const childMsg = ref('No child msg yet')

</script>

<template>
  <h1>{{ title }}</h1>
  <GettingStarted :section="1" />
  <DeclarativeRendering :section="2" />
  <AttributesBinding :section="3" />
  <EventListeners :section="4" />
  <FormBindings :section="5" />
  <ConditionalRendering :section="6" />
  <ListRendering :section="7" />
  <ComputedProperty :section="8" />
  <LifecycleAndTemplateRefs :section="9" />
  <Watchers :section="10" />
  <Component :section="11" />
  <Props :section="12" :msg="greeting" />
  <!-- Init Emit section -->
  <Emit :section="13" @response="(msg) => childMsg = msg" />
  <p>{{ childMsg }}</p>
  <!-- End Emit section -->
</template>
