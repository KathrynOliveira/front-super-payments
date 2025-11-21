<!-- components/StatusCard.vue -->
<script setup>
defineProps({
    title: String,
    value: String,
    count: String,
    percent: String,
    badge: {
        type: Boolean,
        default: false,
    }
});
</script>

<template>
    <div class="bg-white rounded-xl border border-[#EEEEEE] w-[305px] h-[155px] flex flex-col justify-between">
        <!-- Título + Badge + Botão % -->
        <div class="flex justify-between items-start pt-4 px-4">
            <div class="flex items-center gap-1">
                <span class="text-[16px] text-[#2A2E33] font-semibold">
                    {{ title }}
                </span>
                <span v-if="badge"
                    class="w-[16px] h-[16px] bg-[#FF9D3A] text-black flex items-center justify-center text-[10px] rounded-full">
                    !
                </span>
            </div>

            <!-- Botão % -->
            <div
                class="w-[46px] h-[46px] gap-2.5 border border-[#E6E6E6] rounded-full flex items-center justify-center text-[#5A5A5A] text-[12px]">
                %
            </div>
        </div>

        <!-- Valor -->
        <span class="text-[20px] font-bold text-black leading-none pb-4 px-4">
            {{ value }}
        </span>

        <div class="border border[1px] border-[#EEEEEE]"></div>

        <!-- Rodapé: quantidade + porcentagem -->
        <div class="flex justify-between text-[14px] text-[#2A2E33] pb-4 px-4">
            <span class="font-medium">{{ count }}</span>
            <span class="font-semibold">{{ percent }}</span>
        </div>
    </div>
</template>
