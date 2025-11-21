<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
    icon: {
        type: String,
        default: null,
    },
    width: {
        type: String,
        default: "251px",
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
});
</script>

<template>
    <button class="flex items-center justify-center rounded-[250px] gap-[63px] border cursor-pointer" :style="{
        width,
        height,
        background,
        borderColor,
    }">

        <!-- Texto -->
        <span class="font-semibold text-[14px] leading-none text-[#2A2E33]">
            {{ text }}
        </span>
        <!-- Ícone -->
        <img v-if="icon" :src="icon" alt="icon" class="w-5 h-5" />
    </button>
</template>
