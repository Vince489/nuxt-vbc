<template>
  <div class="game-mode-card">
    <div class="icon-container">
      <Icon :name="props.icon" class="game-icon" />
    </div>
    <h3 class="game-title">{{ props.title }}</h3>
    <p class="game-description">{{ props.description }}</p>
  </div>
</template>

<script setup>
const props = defineProps({
  icon: {
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
  }
});
</script>

<style scoped>
.game-mode-card {
  background-color: #2d3748;
  border-radius: 12px;
  padding: 24px;
  text-align: center;
  color: white;
  min-height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transition: transform 0.2s ease;
}

.game-mode-card:hover {
  transform: translateY(-5px);
}

.icon-container {
  display: flex;
  justify-content: center;
  margin-bottom: 16px;
  height: 60px;
}

.game-icon {
  width: 40px;
  height: 40px;
  color: #4299e1;
}

.game-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 8px;
}

.game-description {
  color: #a0aec0;
  font-size: 0.9rem;
  line-height: 1.4;
}
</style>