<template>
  <div class="text-center">
    <p class="text-lg text-white mb-6">Subscribe to our newsletter for launch updates and special offers:</p>
    <form @submit.prevent="subscribe" class="flex flex-col gap-4">
      <input
          v-model="email"
          type="email"
          placeholder="Enter Your Email"
          required
          class="w-full px-4 py-2 text-lg border-2 border-pink-300 rounded-md focus:outline-none focus:ring-2 focus:ring-pink-200 bg-white bg-opacity-20 text-white placeholder-gray-300"
      >
      <button
          type="submit"
          class="w-full px-6 py-2 text-lg bg-pink-400 text-white rounded-md hover:bg-pink-500 transition-colors duration-300"
      >
        Subscribe
      </button>
    </form>
  </div>
</template>

<script setup>
import {ref} from 'vue'

const email = ref('')
const emit = defineEmits(['subscribed'])

const subscribe = () => {
  // Mock subscription logic
  console.log(`Subscribing email: ${email.value}`)
  emit('subscribed', email.value)
  email.value = ''
}
</script>
