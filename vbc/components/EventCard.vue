<template>
  <div class="bg-gray-800 rounded-xl overflow-hidden transition-all duration-300 hover:shadow-2xl hover:-translate-y-1">
    <!-- Image -->
    <div class="h-32 bg-gray-700 flex items-center justify-center">
      <span class="text-gray-500 text-sm">Promoter Image</span>
    </div>

    <!-- Content -->
    <div class="p-5">
      <h3 class="text-xl font-bold text-white mb-2">{{ title }}</h3>
      <p :class="dateColorClass">📅 {{ date }} | {{ time }}</p>
      <p class="text-gray-400 text-xs mb-3">{{ description }}</p>
      <div class="flex justify-between text-gray-500 text-xs mb-4">
        <span>{{ accessType }}</span>
        <a href="#" class="text-red-500 hover:underline">Details</a>
      </div>
      <button :class="buttonColorClass">
        {{ buttonText }}
      </button>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  title: {
    type: String,
    required: true
  },
  date: {
    type: String,
    required: true
  },
  time: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  accessType: {
    type: String,
    default: "🎟️ Premium Access"
  },
  buttonText: {
    type: String,
    default: "Set Reminder / Purchase"
  },
  buttonColor: {
    type: String,
    default: "blue"
  },
  dateColor: {
    type: String,
    default: "blue"
  }
})

const dateColorClass = computed(() => {
  const colorMap = {
    'red': 'text-red-400 text-sm mb-1',
    'blue': 'text-blue-400 text-sm mb-1',
    'purple': 'text-purple-400 text-sm mb-1',
    'green': 'text-green-400 text-sm mb-1'
  }
  return colorMap[props.dateColor] || 'text-blue-400 text-sm mb-1'
})

const buttonColorClass = computed(() => {
  const colorMap = {
    'red': 'w-full bg-red-600 hover:bg-red-700 text-white font-semibold py-2.5 rounded-md transition-colors',
    'blue': 'w-full bg-blue-600 hover:bg-blue-700 text-white font-semibold py-2.5 rounded-md transition-colors',
    'purple': 'w-full bg-purple-600 hover:bg-purple-700 text-white font-semibold py-2.5 rounded-md transition-colors',
    'green': 'w-full bg-green-600 hover:bg-green-700 text-white font-semibold py-2.5 rounded-md transition-colors'
  }
  return colorMap[props.buttonColor] || 'w-full bg-blue-600 hover:bg-blue-700 text-white font-semibold py-2.5 rounded-md transition-colors'
})
</script>
