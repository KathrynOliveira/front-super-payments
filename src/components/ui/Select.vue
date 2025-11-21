<script setup>
defineProps({
    text: String,
    options: Array,
    iconLeft: {
        type: String,
        default: null,
    },
    iconRight: {
        type: String,
        default: '/img/icons/icon-arrow-down.svg',
    },
});
</script>

<template>
    <div
        class="flex items-center gap-2 bg-white rounded-[250px] border border-[#D9D9D9] px-4 h-[46px] min-w-[200px] cursor-pointer">
        <img v-if="iconLeft" :src="iconLeft" class="w-[18px] h-[18px]" />

        <span class="text-[14px] font-semibold text-[#2A2E33] whitespace-nowrap">
            {{ text }}
        </span>

        <img v-if="iconRight" :src="iconRight" class="w-[16px] h-[16px] ml-auto" />
    </div>
</template>
