<script setup>
import { defineProps } from 'vue'
import Counter from './Counter.vue'
import Directive from './Directive.vue'
import PageOne from './PageOne.vue'
import PageTwo from './PageTwo.vue'
import PageThree from './PageThree.vue'
import PageFour from './PageFour.vue'
import PageFive from './PageFive.vue'
import PageSix from './PageSix.vue'
import PageSeven from './PageSeven.vue'
import PageEight from './PageEight.vue'
import PageNine from './PageNine.vue'
import PageTen from './PageTen.vue'
import PageEleven from './PageEleven.vue'
import PageTwelve from './PageTwelve.vue'
import PageThirteen from './PageThirteen.vue'
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
    <PageFour v-if="activeView === 'pageFour'" />
    <PageFive v-if="activeView === 'pageFive'" />
    <PageSix v-if="activeView === 'pageSix'" />
    <PageSeven v-if="activeView === 'pageSeven'" />
    <PageEight v-if="activeView === 'pageEight'" />
    <PageNine v-if="activeView === 'pageNine'" />
    <PageTen v-if="activeView === 'pageTen'" />
    <PageEleven v-if="activeView === 'pageEleven'" />
    <PageTwelve v-if="activeView === 'pageTwelve'" />
    <PageThirteen v-if="activeView === 'pageThirteen'" />
  </div>
</template>

<style scoped>
</style>
