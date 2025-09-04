<template>
  <div :class="cardClasses">
    <Icon :name="icon" class="text-4xl mb-4" />
    <h3 class="text-xl font-bold mb-2">{{ title }}</h3>
    <p :class="descriptionClasses">{{ description }}</p>
    <button :class="buttonClasses" @click="handleClick">
      {{ buttonText }}
    </button>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  icon: {
    type: String,
    required: true
  },
  color: {
    type: String,
    default: 'blue'
  },
  buttonText: {
    type: String,
    required: true
  }
})

const emit = defineEmits(['click'])

const handleClick = () => {
  emit('click')
}

const cardClasses = computed(() => {
  const colorMap = {
    'blue': 'bg-gradient-to-br from-blue-600 to-blue-800',
    'red': 'bg-gradient-to-br from-red-600 to-red-800',
    'green': 'bg-gradient-to-br from-green-600 to-green-800',
    'purple': 'bg-gradient-to-br from-purple-600 to-purple-800',
    'orange': 'bg-gradient-to-br from-orange-600 to-orange-800',
    'teal': 'bg-gradient-to-br from-teal-600 to-teal-800'
  }
  return `${colorMap[props.color] || colorMap.blue} rounded-xl p-6 text-center card-hover`
})



const descriptionClasses = computed(() => {
  const colorMap = {
    'blue': 'text-blue-100',
    'red': 'text-red-100',
    'green': 'text-green-100',
    'purple': 'text-purple-100',
    'orange': 'text-orange-100',
    'teal': 'text-teal-100'
  }
  return `${colorMap[props.color] || colorMap.blue} text-sm mb-4`
})

const buttonClasses = computed(() => {
  const colorMap = {
    'blue': 'w-full bg-white text-blue-800 font-semibold py-2 rounded-lg hover:bg-blue-50 transition-colors',
    'red': 'w-full bg-white text-red-800 font-semibold py-2 rounded-lg hover:bg-red-50 transition-colors',
    'green': 'w-full bg-white text-green-800 font-semibold py-2 rounded-lg hover:bg-green-50 transition-colors',
    'purple': 'w-full bg-white text-purple-800 font-semibold py-2 rounded-lg hover:bg-purple-50 transition-colors',
    'orange': 'w-full bg-white text-orange-800 font-semibold py-2 rounded-lg hover:bg-orange-50 transition-colors',
    'teal': 'w-full bg-white text-teal-800 font-semibold py-2 rounded-lg hover:bg-teal-50 transition-colors'
  }
  return colorMap[props.color] || colorMap.blue
})
</script>