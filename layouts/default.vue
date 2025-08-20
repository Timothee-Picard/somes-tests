<template>
  <div class="min-h-screen flex flex-col">
    <header class="bg-gray-800 text-white flex justify-between items-center p-4">
      <NuxtLink to="/" class="font-bold">some test de Timothee</NuxtLink>
      <a href="https://github.com/Timothee-Picard" target="_blank" class="underline">GitHub</a>
    </header>
    <div class="flex flex-1">
      <aside class="w-64 bg-gray-100 p-4">
        <div>
          <button @click="cssOpen = !cssOpen" class="w-full text-left font-semibold mb-2">CSS Animations</button>
          <ul v-show="cssOpen" class="mb-4 space-y-1">
            <li><NuxtLink to="/animated-shape" class="text-blue-600 hover:underline">Animated shape</NuxtLink></li>
            <li><NuxtLink to="/card-hover" class="text-blue-600 hover:underline">Card hover</NuxtLink></li>
            <li><NuxtLink to="/section" class="text-blue-600 hover:underline">Section</NuxtLink></li>
          </ul>
        </div>
        <div>
          <button @click="jsOpen = !jsOpen" class="w-full text-left font-semibold mb-2">JS Animations</button>
          <ul v-show="jsOpen" class="space-y-1">
            <li><NuxtLink to="/side-slider" class="text-blue-600 hover:underline">Side slider</NuxtLink></li>
            <li><NuxtLink to="/updown-slider" class="text-blue-600 hover:underline">Up/down slider</NuxtLink></li>
            <li><NuxtLink to="/section-scroll" class="text-blue-600 hover:underline">Section scroll</NuxtLink></li>
          </ul>
        </div>
      </aside>
      <main class="flex-1 p-4">
        <NuxtPage />
      </main>
    </div>
  </div>
</template>

<script setup lang="ts">
const cssOpen = ref(true)
const jsOpen = ref(true)
</script>
