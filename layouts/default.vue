<template>
  <div class="flex">
    <!-- Sidebar -->
    <div
      :class="{
        'w-16': collapsed,
        'w-64': !collapsed
      }"
      class="bg-gray-800 text-white h-screen transition-all duration-300 ease-in-out"
    >
      <div class="flex justify-between items-center p-4">
        <!-- Button to toggle the sidebar -->
        <button @click="toggleSidebar" class="text-white focus:outline-none">
          <svg v-if="collapsed" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24" class="feather feather-menu">
            <path d="M3 12h18M3 6h18M3 18h18"></path>
          </svg>
          <svg v-if="!collapsed" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24" class="feather feather-chevron-left">
            <path d="M15 19l-7-7 7-7"></path>
          </svg>
        </button>

        <!-- Title for the sidebar -->
        <div v-show="!collapsed" class="ml-2">My Application</div>
      </div>
      <!-- Sidebar Links -->
      <ul class="space-y-2">
        <li><NuxtLink to="/" class="text-white">Dashboard</NuxtLink></li>
        <li><NuxtLink to="/about" class="text-white">About</NuxtLink></li>
        <li><NuxtLink to="/products" class="text-white">Products</NuxtLink></li>
      </ul>
    </div>

    <!-- Main Content Area -->
    <div class="flex-1 p-4">
      <header class="shadow-sm bg-white mb-4">
        <nav class="container mx-auto p-4 flex justify-between">
          <NuxtLink to="/" class="font-bold">Nuxt</NuxtLink>
          <ul class="flex gap-4">
            <li><NuxtLink to="/">Home</NuxtLink></li>
            <li><NuxtLink to="/about">About</NuxtLink></li>
            <li><NuxtLink to="/products" class="btn">Products</NuxtLink></li>
          </ul>
        </nav>
      </header>
      <!-- Page Content -->
      <div class="container mx-auto p-4">
        <slot />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// Collapse state for the sidebar
const collapsed = ref(false)

// Function to toggle the sidebar between collapsed and expanded
const toggleSidebar = () => {
  collapsed.value = !collapsed.value
}
</script>

<style scoped>
/* Optional styling for your layout */
</style>
