<script setup>
import Navbar from './components/Navbar.vue'
import NavigationDrawer from './components/NavigationDrawer.vue'
import DashboardMain from './components/Dashboard/index.vue'
</script>

<template>
  <div class="h-screen flex flex-col">

    <!-- Navbar -->
    <header>
      <Navbar />
    </header>

    <!-- Layout principal: Drawer + Main lado a lado -->
    <div class="flex flex-1">

      <!-- Drawer -->
      <NavigationDrawer />

      <!-- Main -->
      <main class="flex-1 flex justify-center">
        <DashboardMain />
      </main>

    </div>
  </div>
</template>

<style scoped></style>
