<script setup lang="ts">
import { type PlotlyLayout, type PlotlyConfig } from '../types'

interface Props {
  data: []
  layout?: Partial<PlotlyLayout>
  config?: Partial<PlotlyConfig>
}

defineProps<Props>()
</script>

<template>
  <div ref="chart">this is it</div>
</template>