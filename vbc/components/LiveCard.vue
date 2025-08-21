<template>
  <div class="bg-gray-800 rounded-xl overflow-hidden card-hover">
    <div class="relative">
      <img :src="imageSrc" :alt="title" class="w-full h-40 md:h-56 object-cover object-center">
      <div class="absolute top-3 left-3 bg-red-600 px-2 py-1 rounded text-sm font-semibold">
        🔴 LIVE
      </div>
      <div class="absolute top-3 right-3 bg-black/70 px-2 py-1 rounded text-sm">
        {{ viewers }} viewers
      </div>
    </div>
    <div class="p-4">
      <h3 class="font-bold mb-2">{{ title }}</h3>
      <p class="text-gray-400 text-sm mb-3">{{ description }}</p>
      <button class="w-full bg-red-600 hover:bg-red-700 py-2 rounded-lg transition-colors">
        Watch Live
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps({
  imageSrc: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  viewers: {
    type: [String, Number],
    required: true
  }
})
</script>
