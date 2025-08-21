<template>
  <div class="bg-gray-800 rounded-xl overflow-hidden transition-all duration-300 hover:shadow-2xl hover:-translate-y-1">
    <!-- Image -->
    <div class="h-32 bg-gray-700 flex items-center justify-center">
      <span class="text-gray-500 text-sm">Promoter Image</span>
    </div>

    <!-- Content -->
    <div class="p-5">
      <h3 class="text-xl font-bold text-white mb-2">{{ title }}</h3>
      <p :class="`text-${dateColor}-400 text-sm mb-1`">📅 {{ date }} | {{ time }}</p>
      <p class="text-gray-400 text-xs mb-3">{{ description }}</p>
      <div class="flex justify-between text-gray-500 text-xs mb-4">
        <span>{{ accessType }}</span>
        <a href="#" class="text-red-500 hover:underline">Details</a>
      </div>
      <button :class="`w-full bg-${buttonColor}-600 hover:bg-${buttonColor}-700 text-white font-semibold py-2.5 rounded-md transition-colors`">
        {{ buttonText }}
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps({
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
</script>
