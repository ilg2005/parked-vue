<template>
  <div class="min-h-screen bg-cover bg-center flex items-center justify-center p-4 relative"
       :style="{ backgroundImage: 'url(https://picsum.photos/1920/1080)' }">
    <div class="absolute inset-0 bg-blue-900 bg-opacity-60"></div>

    <div class="relative z-10 flex flex-col items-center gap-8 max-w-lg mx-auto">
      <Heading title="Coming Soon..." />
      <Countdown :endDate="endDate" />

      <div class="flex flex-col items-center gap-3">
        <svg class="w-16 h-16 text-pink-300 animate-spin" style="animation-duration: 8s" fill="none" viewBox="0 0 24 24">
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 15a3 3 0 1 0 0-6 3 3 0 0 0 0 6Z"/>
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06A1.65 1.65 0 0 0 4.68 15a1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06A1.65 1.65 0 0 0 9 4.68a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06A1.65 1.65 0 0 0 19.4 9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1Z"/>
        </svg>
        <p class="text-base text-white font-medium">Under Development</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Heading from '@/components/Heading.vue'
import Countdown from '@/components/Countdown.vue'

const endDate = ref(new Date().getTime() + 4 * 24 * 60 * 60 * 1000) // 4 дня с текущего момента
</script>
