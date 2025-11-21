<template>
    <nav class="w-full h-[77px] bg-white border-b border-[#EEEEEE] flex items-center px-8">
        <!-- Logo -->
        <div class="flex items-center gap-3">
            <img src="/img/logo.svg" alt="Logo" class="w-[130px] h-[30px]" />
        </div>

        <!-- Title -->
        <h1 class="ml-[180px] text-[20px] font-bold leading-none text-black">
            Super central de gestão
            <img src="/img/icons/icon-super.svg" class="inline-block w-5 h-5 ml-2" />
        </h1>

        <div class="ml-auto flex items-center gap-4">
            <!-- Icons -->
            <div class="w-8 h-8 p-[6px] rounded-lg flex items-center justify-center hover:bg-gray-100 cursor-pointer">
                <img src="/img/icons/icon1.svg" class="w-[32px] h-[32px]" />
            </div>

            <div class="w-8 h-8 p-[6px] rounded-lg flex items-center justify-center hover:bg-gray-100 cursor-pointer">
                <img src="/img/icons/icon2.svg" class="w-[32px] h-[32px]" />
            </div>

            <div class="w-8 h-8 p-[6px] rounded-lg flex items-center justify-center hover:bg-gray-100 cursor-pointer">
                <img src="/img/icons/icon3.svg" class="w-[32px] h-[32px]" />
            </div>

            <!-- AP Circle -->
            <div
                class="w-9 h-9 rounded-full bg-primary flex items-center justify-center text-white text-sm font-semibold">
                AP
            </div>

            <!-- Texto empresarial + seta -->
            <div class="flex items-center gap-2">
                <div class="flex flex-col leading-none">
                    <span class="text-[12px] font-semibold text-[#11151B]">
                        Empresarial
                    </span>
                    <span class="text-[12px] font-semibold text-[#86898B]">
                        Astra Pagamentos
                    </span>
                </div>
                <!-- <img src="/arrow-down.svg" class="w-4 h-4" /> -->
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    name: "NavbarLayout",
};
</script>

<style scoped></style>
