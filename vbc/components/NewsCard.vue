<template>
  <div class="bg-gray-700 rounded-lg overflow-hidden">
    <img :src="imageSrc" :alt="imageAlt" class="w-full h-40 object-cover">
    <div class="p-4">
      <h4 class="text-lg font-semibold text-white mb-2">{{ title }}</h4>
      <p class="text-gray-300 text-sm mb-3">{{ description }}</p>
      <a href="#" class="text-blue-400 hover:underline text-sm">
        {{ linkText }} <i :class="linkIcon" class="ml-1"></i>
      </a>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  imageSrc: {
    type: String,
    required: true
  },
  imageAlt: {
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
  linkText: {
    type: String,
    required: true
  },
  linkIcon: {
    type: String,
    default: 'fas fa-arrow-right'
  }
})
</script>
