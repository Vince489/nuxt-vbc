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
</style>
