<script setup>
defineProps({
    icon: {
        type: String,
        required: true,
    },
    background: {
        type: String,
        default: "#FFFFFF",
    },
    color: {
        type: String,
        default: "#2A2E33",
    },
    borderColor: {
        type: String,
        default: "#D9D9D9",
    },
});
</script>

<template>
    <button class="flex items-center justify-center rounded-full cursor-pointer" :style="{
        width: '46px',
        height: '46px',
        background,
        border: `1px solid ${borderColor}`,
        padding: '6px 23px',
    }">
    {{ icon }}
        <img v-if="icon" :src="icon" alt="icon" class="w-[20px] h-[20px]" />
    </button>
</template>
