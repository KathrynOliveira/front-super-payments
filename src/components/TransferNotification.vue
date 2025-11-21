<script setup>

import Button from './ui/Button.vue';

</script>

<template>
    <div class="w-full bg-white rounded-full px-6 py-4 flex items-center justify-between shadow-sm">
        <div class="flex items-center gap-4">
            <!-- ÍCONE CÍRCULO -->
            <div class="relative flex items-center justify-center w-[50px] h-[50px] rounded-full bg-[#E6E3DC]">
                <img src="/img/icons/icon-arrow-up.svg" class="w-[20px] h-[20px]" />
                <!-- BADGE -->
                <span
                    class="absolute bottom-[2px] right-[2px] w-[15px] h-[15px] bg-[#FF9F0A] rounded-full border border-white"></span>
            </div>
            <!-- TEXTOS -->
            <div class="flex flex-col leading-none">
                <span class="text-[16px] font-semibold text-[#2A2E33]">
                    Solicitação de transferência pendente
                </span>
                <span class="text-[12px] font-semibold text-[#86898B] mt-1">
                    A transação no valor de R$ 29.119,13 está aguardando a sua aprovação.
                </span>
            </div>
        </div>

        <!-- BOTÃO -->
        <Button text="Autorizar transferência" background="#0641FC" icon-right="/img/icons/icon-wallet-money.svg"
            color="#F9F9F9" />
    </div>
</template>
