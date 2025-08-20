<template>
  <div class="min-h-screen flex flex-col">
    <nav class="bg-gray-800 text-white flex items-center justify-between px-4 py-3">
      <NuxtLink to="/" class="text-xl font-bold">some test de Timothee</NuxtLink>
      <a
        href="https://github.com/Timothee-Picard"
        target="_blank"
        class="text-sm underline hover:text-gray-300"
      >
        GitHub
      </a>
    </nav>
    <div class="flex flex-1">
      <nav class="w-64 bg-gray-100 p-4 space-y-6">
        <div>
          <button
            @click="cssOpen = !cssOpen"
            class="w-full text-left font-semibold mb-2"
          >
            CSS Animations
          </button>
          <ul v-show="cssOpen" class="mb-4 space-y-1">
            <li>
              <NuxtLink to="/animated-shape" class="block px-2 py-1 rounded hover:bg-gray-200"
                >Animated shape</NuxtLink
              >
            </li>
            <li>
              <NuxtLink to="/card-hover" class="block px-2 py-1 rounded hover:bg-gray-200"
                >Card hover</NuxtLink
              >
            </li>
            <li>
              <NuxtLink to="/section" class="block px-2 py-1 rounded hover:bg-gray-200"
                >Section</NuxtLink
              >
            </li>
          </ul>
        </div>
        <div>
          <button
            @click="jsOpen = !jsOpen"
            class="w-full text-left font-semibold mb-2"
          >
            JS Animations
          </button>
          <ul v-show="jsOpen" class="space-y-1">
            <li>
              <NuxtLink to="/side-slider" class="block px-2 py-1 rounded hover:bg-gray-200"
                >Side slider</NuxtLink
              >
            </li>
            <li>
              <NuxtLink to="/updown-slider" class="block px-2 py-1 rounded hover:bg-gray-200"
                >Up/down slider</NuxtLink
              >
            </li>
            <li>
              <NuxtLink to="/section-scroll" class="block px-2 py-1 rounded hover:bg-gray-200"
                >Section scroll</NuxtLink
              >
            </li>
          </ul>
        </div>
      </nav>
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
