<script setup lang="ts">
import { ref } from 'vue';

const gameModes = ref([
  {
    icon: 'uil:user-circle',
    title: 'Legacy Mode',
    description: 'Forge your legend from amateur to champion.'
  },
  {
    icon: 'uil:trophy',
    title: 'Tournaments',
    description: 'Compete for glory in structured events.'
  },
  {
    icon: 'iconoir:boxing-glove',
    title: 'Custom Fight',
    description: 'Set your own rules for ultimate control.'
  },
  {
    icon: 'uil:users-alt',
    title: 'Multiplayer Arena',
    description: 'Challenge players worldwide.'
  },
  {
    icon: 'uil:user-plus',
    title: 'Friend Match',
    description: 'Fight your friends head-to-head.'
  },
  {
    icon: 'uil:book-open',
    title: 'Fighter Roster',
    description: 'Browse all available fighters.'
  }
]);
</script>

<template>
  <div class="game-modes-container">
    <h1 class="section-title">Game Modes</h1>
    <div class="game-modes-grid">
      <GameModeCard
        v-for="(mode, index) in gameModes"
        :key="index"
        :icon="mode.icon"
        :title="mode.title"
        :description="mode.description"
      />
    </div>
  </div>
</template>

<style scoped>
.game-modes-container {
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.section-title {
  color: white;
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 2rem;
  text-align: left;
}

.game-modes-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

@media (max-width: 1024px) {
  .game-modes-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .game-modes-grid {
    grid-template-columns: 1fr;
  }
}
</style>
