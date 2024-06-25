<template>
  <header class="text-center mb-8">
    <h1 class="text-4xl sm:text-5xl font-bold text-pink-300">{{ title }}</h1>
  </header>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  }
})
</script>
