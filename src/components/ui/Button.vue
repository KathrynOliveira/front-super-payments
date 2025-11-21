<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
    iconLeft: {
        type: String,
        default: null,
    },
    iconRight: {
        type: String,
        default: null,
    },
    width: {
        type: String,
        default: "auto",
    },
    height: {
        type: String,
        default: "46px",
    },
    background: {
        type: String,
        default: "#FFFFFF",
    },
    borderColor: {
        type: String,
        default: "#D9D9D9",
    },
    color: {
        type: String,
        default: "#2A2E33",
    },
});
</script>

<template>
    <button class="flex items-center rounded-[250px] gap-2 px-4 border cursor-pointer"
        :style="{ width, height, background, borderColor }">
        <!-- Ícone esquerdo -->
        <img v-if="iconLeft" :src="iconLeft" class="w-[18px] h-[18px]" />

        <!-- Texto -->
        <span class="font-semibold text-[14px] leading-none" :style="{ color }">
            {{ text }}
        </span>

        <!-- Ícone direito -->
        <img v-if="iconRight" :src="iconRight" class="w-[18px] h-[18px]" />
    </button>
</template>
