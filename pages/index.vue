<script setup>
import {VueFlow} from '@vue-flow/core'
import {ref} from '#imports'

const elements = ref([
  {
    id: '1',
    type: 'input',
    label: 'Node 1',
    position: {x: 250, y: 5},
  },
])
</script>

<template>
  <div class="page">
    <VueFlow v-model="elements">
      <template #connection-line="{ sourceX, sourceY, targetX, targetY }">
        <CustomConnectionLine :source-x="sourceX" :source-y="sourceY" :target-x="targetX" :target-y="targetY"/>
      </template>
    </VueFlow>
  </div>
</template>

<style>
@import '@vue-flow/core/dist/style.css';
@import '@vue-flow/core/dist/theme-default.css';
</style>

<style scoped>
.page {
  width: 100vw;
  height: 100vh;
}
</style>