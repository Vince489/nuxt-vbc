<script setup lang="ts">
import { ref } from 'vue';

const newsItems = ref([
  {
    imageSrc: "https://placehold.co/600x300/374151/FFFFFF?text=News+Image+1",
    imageAlt: "News Image",
    title: "Patch 1.2.0 - New Fighters & Balance Changes!",
    description: "Read about the latest updates to the game, including two new heavyweight contenders and crucial balance adjustments.",
    linkText: "Read More",
    linkIcon: "fas fa-arrow-right"
  },
  {
    imageSrc: "https://placehold.co/600x300/374151/FFFFFF?text=Highlight+Video",
    imageAlt: "Highlight Video",
    title: "Top 5 Knockouts of the Month!",
    description: "Witness the most devastating KOs from the community in our latest highlight reel.",
    linkText: "Watch Video",
    linkIcon: "fas fa-play-circle"
  },
  {
    imageSrc: "https://placehold.co/600x300/374151/FFFFFF?text=News+Image+2",
    imageAlt: "News Image",
    title: "Developer Livestream Replay: Q&A with the Devs!",
    description: "Catch up on the recent Q&A session with the Virtron development team.",
    linkText: "Watch Replay",
    linkIcon: "fas fa-video"
  }
]);
</script>

<template>
  <div class="news-container">
    <h1 class="section-title">Latest News</h1>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      <NewsCard
        v-for="(item, index) in newsItems"
        :key="index"
        :image-src="item.imageSrc"
        :image-alt="item.imageAlt"
        :title="item.title"
        :description="item.description"
        :link-text="item.linkText"
        :link-icon="item.linkIcon"
      />
    </div>
  </div>
</template>

<style scoped>
.news-container {
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
</style>
