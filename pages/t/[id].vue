<template>
    <div>
        <h1>Detail page '{{ route.params.id }}'</h1>
        <Line :data="data" />
    </div>
</template>

<script lang="ts" setup>
import { Chart, Line } from "vue-chartjs"
const route = useRoute()

import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend
} from 'chart.js'

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend
)

const numericData = ref<number[]>([])
for (let i = 0; i < 100; i++) {
    numericData.value.push(Math.sin(i/10))
}

const labelKeys = []
for (let i = 0; i < numericData.value.length; i++) {
    labelKeys.push(i)
}

const data = {
    labels: labelKeys,
    datasets: [
        {
            label: 'Data One',
            backgroundColor: '#f87979',
            data: numericData.value,
        }
    ]
} 
</script>

