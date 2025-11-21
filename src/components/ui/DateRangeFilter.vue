<script setup>
defineProps({
    startDate: String,
    endDate: String,
    icon: String,
});
</script>

<template>
    <div class="flex items-center bg-white rounded-[250px] border border-[#D9D9D9] px-4 h-[46px] cursor-pointer gap-2">

        <!-- Ícone -->
        <img :src="icon" class="w-[18px] h-[18px]" />

        <!-- Data inicial -->
        <span class="text-[14px] font-semibold text-[#2A2E33]">
            {{ startDate }}
        </span>

        <!-- Separador -->
        <span class="text-[18px] font-bold text-[#CED0D4]">|</span>

        <!-- Data final -->
        <span class="text-[14px] font-semibold text-[#2A2E33]">
            {{ endDate }}
        </span>

        <!-- Ícone seta -->
        <img src="/img/icons/icon-arrow-down.svg" class="w-[16px] h-[16px] ml-auto" />
    </div>
</template>
