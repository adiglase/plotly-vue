<script setup lang="ts">
import Plotly from 'plotly.js-dist-min';
import { onMounted, useTemplateRef, watchEffect } from 'vue';

const props = defineProps<{
  data: Plotly.Data[],
  layout?: Partial<Plotly.Layout>,
  config?: Partial<Plotly.Config>,
}>()

const chartContainer = useTemplateRef('chart-container')

onMounted(() => {
  if (chartContainer.value) {
    Plotly.newPlot(chartContainer.value, props.data, props.layout, props.config)
  }
})

watchEffect(() => {
  if (chartContainer.value) {
    Plotly.react(chartContainer.value, props.data, props.layout, props.config)
  }
})
</script>

<template>
  <div class="chart-container" ref="chart-container"></div>
</template>
