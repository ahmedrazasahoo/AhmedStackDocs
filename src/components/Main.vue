<script setup>
import { defineProps } from 'vue'
import Counter from './Counter.vue'
import Directive from './Directive.vue'
import PageOne from './PageOne.vue'
import PageTwo from './PageTwo.vue'
import PageThree from './PageThree.vue'
defineProps({
  activeView: {
    type: String,
    default: 'one'
  }
})
</script>

<template>
  <div>
    <Counter v-if="activeView === 'one'" />
    <Directive v-if="activeView === 'two'" />
    <div v-if="activeView === 'three'">
      <Counter />
      <Directive />
    </div>
    <PageOne v-if="activeView === 'pageOne'" />
    <PageTwo v-if="activeView === 'pageTwo'" />
    <PageThree v-if="activeView === 'pageThree'" />
  </div>
</template>

<style scoped>
</style>
