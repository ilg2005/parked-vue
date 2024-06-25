<template>
  <div class="min-h-screen bg-cover bg-center flex flex-col justify-between items-center p-4 sm:p-8 relative"
       :style="{ backgroundImage: 'url(https://picsum.photos/1920/1080)' }">
    <div class="absolute inset-0 bg-blue-900 bg-opacity-50"></div>

    <section class="w-full text-center relative z-10 mt-4">
      <Heading title="Coming Soon..." />
    </section>

    <main class="relative z-10 flex flex-col justify-center items-center h-full max-w-4xl mx-auto">
      <Countdown :endDate="endDate" />
    </main>

    <section class="max-w-md text-center relative z-10 mb-20 px-10">
      <Subscribe @subscribed="onSubscribed" />
    </section>
  </div>

  <ModalSuccess
      :show="showModal"
      :email="subscribedEmail"
      @close="showModal = false"
  />
</template>

<script setup>
import { ref } from 'vue'
import Heading from '@/components/Heading.vue'
import Countdown from '@/components/Countdown.vue'
import Subscribe from '@/components/Subscribe.vue'
import ModalSuccess from '@/components/ModalSuccess.vue'

const endDate = ref(new Date().getTime() + 4 * 24 * 60 * 60 * 1000) // 4 дня с текущего момента
const showModal = ref(false)
const subscribedEmail = ref('')

const onSubscribed = (email) => {
  subscribedEmail.value = email
  showModal.value = true
}
</script>
