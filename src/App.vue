<script setup>
import Navbar from './components/Navbar.vue'
import NavigationDrawer from './components/NavigationDrawer.vue'
</script>

<template>
  <div class="flex h-screen">
    <!-- Conteúdo principal -->
    <div class="flex-1 flex flex-col">

      <!-- Navbar -->
      <header>
        <Navbar />
      </header>
      <!-- Sidebar -->
      <NavigationDrawer />

      <!-- Main content -->
      <!-- <main class="flex-1 bg-gray-50">

      </main> -->

    </div>
  </div>
</template>

<style scoped></style>
