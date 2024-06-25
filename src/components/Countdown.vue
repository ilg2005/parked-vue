<template>
  <p class="text-lg sm:text-xl text-white mb-6">
    Our new website will be online in:
  </p>
  <div class="grid grid-cols-2 sm:grid-cols-4 gap-4 text-white">
    <div v-for="(value, key) in timeLeft" :key="key" class="bg-pink-500 bg-opacity-50 rounded-lg p-4">
      <span class="block text-4xl font-bold">{{ value }}</span>
      <span class="text-sm">{{ key }}</span>
    </div>
  </div>
</template>

<script setup>
import { reactive, onMounted, onUnmounted } from 'vue'

const props = defineProps({
  endDate: {
    type: Number,
    required: true
  }
})

const timeLeft = reactive({
  days: 0,
  hours: 0,
  minutes: 0,
  seconds: 0
})

const updateCountdown = () => {
  const now = new Date().getTime()
  const distance = props.endDate - now

  timeLeft.days = Math.floor(distance / (1000 * 60 * 60 * 24))
  timeLeft.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
  timeLeft.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60))
  timeLeft.seconds = Math.floor((distance % (1000 * 60)) / 1000)
}

let timer

onMounted(() => {
  updateCountdown()
  timer = setInterval(updateCountdown, 1000)
})

onUnmounted(() => {
  clearInterval(timer)
})
</script>
