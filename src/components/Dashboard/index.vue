<script setup>
import Button from '../ui/Button.vue';
import DateRangeFilter from '../ui/DateRangeFilter.vue'
import Select from '../ui/Select.vue'
import ButtonRounded from '../ui/ButtonRounded.vue';

import CardInvoicing from '../CardInvoicing.vue'
import DashboardColumnChart from './ColumnChart.vue'
import TransferNotification from '../TransferNotification.vue'

// import download from "@/../public/img/icons/icon-download.svg";

const cards = [
    { title: "Faturamento recebido", value: "R$ 245.340,90", icon: "/img/icons/icon-ball-blue.svg", badge: false },
    { title: "Faturamento previsto", value: "R$ 815.210,24", icon: "/img/icons/icon-ball-lilac.svg", badge: true },
    { title: "Vendas pendentes", value: "R$ 15.332,18", icon: "/img/icons/icon-ball-orange.svg", badge: false },
    { title: "Ticket médio", value: "R$ 192,30", icon: "/img/icons/icon-ball-lilac.svg", badge: false },
    { title: "Número de cobranças", value: "12.349", icon: "/img/icons/icon-ball-black.svg", badge: false },
];

</script>

<template>
    <!-- Fundo cinza claro ocupando tudo -->
    <div class="">
        <div class="flex flex-row items-center justify-between my-6 w-full">

            <!-- ESQUERDA -->
            <div class="flex flex-row gap-3 w-5/6">
                <Button text="Nova cobrança" background="#0641FC" width="162px" height="46px" color="#fff" />

                <div class="border-r border-[#D9D9D9] border-[1px]"></div>

                <Button text="Período: Específico" iconLeft="/img/icons/icon-calendar.svg"
                    iconRight="/img/icons/icon-arrow-down.svg" />

                <DateRangeFilter icon="/img/icons/icon-calendar.svg" startDate="10-06-2020" endDate="30-01-2025" />

                <Button text="Tipo de cobrança" />
            </div>

            <!-- DIREITA -->
            <div class="flex flex-row gap-3 w-1/6 justify-end">
                <Select text="Tipo cobrança" width="162px" height="46px" iconLeft="/img/icons/icon-card-transfer.svg" />

                <ButtonRounded icon="/img/icons/icon-download.svg" />
            </div>

        </div>

        <div class=" bg-white rounded-xl p-6 border border-[#EEEEEE]" style="width: 1258px; height: 491px;">
            <!-- TÍTULO -->
            <div class="flex items-center gap-2 mb-6">
                <h2 class="text-[20px] font-bold text-black">Faturamento</h2>
                <img src="/img/icons/icon-eyes.svg" width="25px" height="24px" class="cursor-pointer" />
            </div>
            <!-- VALORES -->
            <div class="flex items-start gap-6 mb-8">
                <div class="flex flex-row gap-3">
                    <span class="text-[#86898B] text-[16px] font-medium">R$</span>

                    <span class="text-[40px] font-bold text-[#0641FC] leading-none">
                        1.060.551,14
                    </span>
                </div>

                <div class="flex flex-col">
                    <span class="text-[12px] font-extrabold text-[#34A853]">
                        ↑ 123,9%
                    </span>
                    <span class="text-[#86898B] text-[12px] font-semibold">
                        Em crescimento
                    </span>
                </div>
            </div>
            <!-- GRÁFICO -->
            <div>
                <DashboardColumnChart />
                <!-- CARDS INFERIORES -->
                <div class="flex flex-row gap-[10px] pt-3" style="width: 1208px; height: 79px;">
                    <CardInvoicing v-for="(item, index) in cards" :key="index" :title="item.title" :value="item.value"
                        :badge="item.badge" :icon="item.icon" />
                </div>
            </div>
        </div>

        <div class="flex flew-row mt-6">
            <TransferNotification icon="/img/icons/icon-arrow-up.svg" buttonIcon="/img/icons/icon-card-transfer.svg" />
        </div>

    </div>
</template>
