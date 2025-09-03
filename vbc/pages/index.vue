<template>
  <div>
    <Navbar @toggle-sidebar="toggleSidebar" />
    <Sidebar ref="sidebarRef" />
    <section class="relative min-h-screen flex items-center justify-center">
      <!-- Background Image -->
      <div class="absolute inset-0">
        <img
          src="/images/banner.png"
          alt="Hero Background"
          class="w-full h-full object-cover"
        />
        <!-- Dark overlay -->
        <div class="absolute inset-0 bg-black/40"></div>
      </div>

      <!-- Hero Content -->
      <div class="">
      <!-- Main Heading -->
    </div>
  </section>

    <!-- Live Now Section -->
    <section class="bg-gray-900 p-6 md:p-8 mb-6">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-white mb-6 pb-2 border-b border-gray-700 flex items-center">
          <span class="animate-pulse w-3 h-3 bg-red-600 rounded-full mr-3"></span>
          Live Now
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <LiveCard
            image-src="/images/jab.png"
            title="Championship Bout: Thunder vs Lightning"
            description="Heavyweight title fight happening now! Don't miss it."
            :viewers="2847"
          />
          <LiveCard
            image-src="/images/will.png"
            title="Amateur Tournament Finals"
            description="Young fighters competing for the amateur championship."
            :viewers="1523"
          />
          <LiveCard
            image-src="/images/lame.png"
            title="Training Session with Pro Fighters"
            description="Watch professional fighters train and share techniques."
            :viewers="892"
          />
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>

const sidebarRef = ref(null);

const toggleSidebar = () => {
  sidebarRef.value?.toggleSidebar();
};
</script>

<style scoped>
.custom-scrollbar::-webkit-scrollbar {
  height: 8px;
}

.custom-scrollbar::-webkit-scrollbar-track {
  background: #2d3748;
  border-radius: 10px;
}

.custom-scrollbar::-webkit-scrollbar-thumb {
  background: #4a5568;
  border-radius: 10px;
}

.custom-scrollbar::-webkit-scrollbar-thumb:hover {
  background: #718096;
}

/* Card hover effect for LiveCard components */
:deep(.card-hover) {
  transition: all 0.3s ease;
}

:deep(.card-hover:hover) {
  transform: translateY(-4px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
}
</style>
