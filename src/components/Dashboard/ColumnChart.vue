<script setup>
import { onMounted } from 'vue'
import ApexCharts from 'apexcharts'

onMounted(() => {

    const baseData = [
        10, 20, 25, 30, 28, 80, 95, 60, 20,
        25, 30, 22, 18, 20, 140, 180, 120,
        35, 22, 50, 18, 40, 55, 70, 65, 80,
        25, 150, 20, 10, 25
    ]

    const options = {
        chart: {
            type: 'bar',
            height: '100%',
            width: '100%',
            toolbar: { show: false },
        },

        grid: {
            borderColor: '#E2E8F0',
            strokeDashArray: 0,
            yaxis: { lines: { show: true } },
            xaxis: { lines: { show: false } },
        },

        plotOptions: {
            bar: {
                borderRadius: 5,
                columnWidth: '25%',
            }
        },

        fill: {
            type: 'gradient',
            gradient: {
                shade: 'light',
                type: "vertical",
                gradientToColors: ['#0641FC'], // azul → verde
                inverseColors: false,
                opacityFrom: 0.95,
                opacityTo: 0.95,
                stops: [0, 80, 100]
            }
        },

        colors: ['#2FCD66'],  // cor base do gradiente (azul)

        series: [
            {
                name: 'Faturamento',
                data: baseData,
            }
        ],

        xaxis: {
            categories: Array.from({ length: 31 }, (_, i) => i + 1),
            labels: {
                style: { colors: '#A0AEC0', fontSize: '12px' }
            },
            axisBorder: { show: false },
            axisTicks: { show: false }
        },

        yaxis: {
            max: 200,
            labels: {
                formatter: value => (value >= 1000 ? value / 1000 + "K" : value),
                style: { colors: '#A0AEC0' }
            }
        },
        
        
        tooltip: {
            theme: 'light',
            y: {
                formatter: val =>
                    `R$ ${val.toLocaleString('pt-BR')}`
            }
        },

        legend: { show: false },
        dataLabels: {
            enabled: false
        },
    }

    const chart = new ApexCharts(document.querySelector('#chart'), options)
    chart.render()
})
</script>

<template>
    <div id="chart" class="w-full h-full"></div>
</template>

<style scoped>
#chart {
    width: 100%;
    height: 100%;
}
</style>
