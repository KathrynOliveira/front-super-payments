<script setup>
import Button from './ui/Button.vue';

const menu = [
    { main: 'Menu', title: 'Dashboard', icon: '/img/icons/icon-dashboard.svg' },
    { main: 'Menu', title: 'Clientes', icon: '/img/icons/icon-clients.svg' },
    { main: 'Menu', title: 'Cobranças', icon: '/img/icons/icon-charge.svg' },
    { main: 'Menu', title: 'Carteira', icon: '/img/icons/icon-wallet.svg' },
    { main: 'Menu', title: 'Vendedores', icon: '/img/icons/icon-sellers.svg' },
    { main: 'Menu', title: 'Antecipações', icon: '/img/icons/icon-anticipations.svg' },
    { main: 'Menu', title: 'Gestão', icon: '/img/icons/icon-management.svg' },
    { main: 'Menu', title: 'Integrações', icon: '/img/icons/icon-integrations.svg' },
    { main: 'Geral', title: 'Configurações', icon: '/img/icons/icon-settings.svg' },
    { main: 'Geral', title: 'Perfil', icon: '/img/icons/icon-user.svg' },
];

// agrupa os itens por MAIN
function groupByMain(list) {
    const groups = {};

    list.forEach(item => {
        if (!groups[item.main]) groups[item.main] = [];
        groups[item.main].push(item);
    });

    return Object.keys(groups).map(main => ({
        main,
        items: groups[main]
    }));
}
</script>

<template>
    <aside class="w-[315px] relative bg-white border-r border-[#EEEEEE] flex flex-col">
        <nav class="flex flex-col gap-4">
            <!-- Agrupar por main -->
            <template v-for="(group, groupIndex) in groupByMain(menu)" :key="groupIndex">

                <!-- TÍTULO DO MAIN -->
                <div class="mt-4">

                    <!-- Texto do MAIN -->
                    <p
                        class="text-[12px] font-bold text-[#86898B] tracking-[12%] leading-[100%] ml-[33px] mt-4 uppercase">
                        {{ group.main }}
                    </p>
                </div>

                <!-- LISTA DE ITENS -->
                <div>
                    <div v-for="(item, index) in group.items" :key="index"
                        class="flex items-center gap-4 cursor-pointer hover:bg-gray-100 p-2 rounded-lg mt-2">
                        <img :src="item.icon" class="w-[42px] h-[41]" />

                        <span class="text-[14px] font-semibold text-[#2A2E33]">
                            {{ item.title }}
                        </span>
                    </div>
                </div>
            </template>
            <div class="flex justify-center">
                <img src="/img/super-card.svg" />
            </div>
            <div class="border border-[#EEEEEE] border[1px]" />

            <div class="flex justify-center px-2 pb-3">
                <Button text="Deslogar da Conta" iconRight="/img/icons/icon-right-arrow.svg" />
            </div>
        </nav>
    </aside>
</template>
