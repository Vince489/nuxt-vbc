<template>
  <div class="bg-gray-800 rounded-lg shadow-sm overflow-hidden hover:shadow-lg transition-shadow duration-300">
    <div class="relative aspect-video bg-gray-700 overflow-hidden rounded-lg">
      <img :src="imageSrc" :alt="title" class="w-full h-full object-cover rounded-lg transition-transform duration-300 hover:scale-110">
      <div class="absolute bottom-2 right-2 bg-black bg-opacity-70 text-white text-xs px-2 py-1 rounded">
        {{ duration }}
      </div>
      <div class="absolute top-2 left-2 bg-black bg-opacity-70 text-white text-xs px-2 py-1 rounded">
        <i class="fas fa-play mr-1"></i>Watch Now
      </div>
    </div>
    <div class="p-4">
      <h3 class="font-bold text-lg mb-1 text-gray-300 hover:text-blue-500">
        <a href="#">{{ title }}</a>
      </h3>
      <div class="text-sm text-gray-400 mb-2">
        <span>{{ views }} views</span>
        <span class="mx-2">•</span>
        <span>{{ timeAgo }}</span>
      </div>
      <div class="flex items-center text-sm text-gray-400">
        <div class="w-8 h-8 rounded-full bg-gray-600 overflow-hidden">
          <img :src="channelIcon" alt="Channel icon" class="w-full h-full object-cover"/>
        </div>
        <div class="ml-2">
          <p class="text-sm">{{ channelName }}</p>
        </div>
      </div>
      <div class="mt-3 bg-gray-700 p-3 rounded-lg">
        <h4 class="font-semibold text-gray-300 mb-1">Fight Details</h4>
        <div class="text-sm text-gray-400">
          <p><span class="font-medium">{{ fighter1 }}</span> vs <span class="font-medium">{{ fighter2 }}</span></p>
          <p class="mt-1">{{ weightClass }} • {{ eventName }}</p>
        </div>
      </div>
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
  duration: {
    type: String,
    required: true
  },
  views: {
    type: String,
    required: true
  },
  timeAgo: {
    type: String,
    required: true
  },
  channelIcon: {
    type: String,
    required: true
  },
  channelName: {
    type: String,
    required: true
  },
  fighter1: {
    type: String,
    required: true
  },
  fighter2: {
    type: String,
    required: true
  },
  weightClass: {
    type: String,
    required: true
  },
  eventName: {
    type: String,
    required: true
  }
})
</script>
