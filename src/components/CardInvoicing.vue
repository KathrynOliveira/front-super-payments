<script setup>
const props = defineProps({
    title: {
        type: String,
        required: true
    },
    value: {
        type: String,
        required: true
    },
    icon: {
        type: String,
        default: null
    },
    badge: {
        type: Boolean,
        default: false
    }
});
</script>

<template>
    <div class="w-[233.6px] h-[79px] bg-white border border-gray-200 rounded-xl flex flex-col px-4 py-3">
        <!-- Título -->
        <div class="flex flex-row justify-between items-center mb-3">
            <span class="text-[12px] font-semibold text-gray-500">
                {{ title }}
            </span>
            <span v-if="badge" class="text-[10px] font-semibold border border[1px] border-[#D9D9D9] rounded-2xl text-[#2A2E33] leading-none px-2 py-1">
                D+2
            </span>
        </div>

        <div class="flex items-center gap-2">
            <!-- Ícone -->
            <img v-if="icon" :src="icon" alt="icon" class="w-[12px] h-[12px]" />

            <!-- Valor -->
            <span class="text-[20px] font-bold text-black leading-none">
                {{ value }}
            </span>
        </div>
    </div>
</template>
