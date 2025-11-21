<script setup>
import ApexCharts from 'apexcharts'
import { onMounted, ref, watch } from 'vue'

const props = defineProps({
    series: { type: Number, required: true },
    title: { type: String, required: true },
    color: { type: String, default: '#0641FC' },
    size: { type: Number, default: 120 }
})

const chartRef = ref(null)

onMounted(() => renderChart())

watch(() => props.series, () => renderChart())

function renderChart() {
    if (!chartRef.value) return

    chartRef.value.innerHTML = ''

    const options = {
        chart: { type: 'radialBar', height: '100%', width: '100%' },
        series: [props.series],
        colors: [props.color],
        plotOptions: {
            radialBar: {
                hollow: { margin: 5, size: '60%' },
                dataLabels: {
                    showOn: 'always',
                    name: { show: false },
                    value: { fontSize: '20px', show: true }
                }
            }
        },
        labels: [props.title]
    }

    const chart = new ApexCharts(chartRef.value, options)
    chart.render()
}
</script>

<template>
    <div class="flex flex-col items-center">
        <div :style="{ width: size + 'px', height: size + 'px' }" ref="chartRef"></div>
        <span class="mt-2 text-[14px] font-semibold text-center">{{ title }}</span>
    </div>
</template>
