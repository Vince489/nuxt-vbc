<template>
  <div class="min-h-screen bg-gray-900 text-white overflow-x-hidden">
    <!-- Navbar -->
    <Navbar @toggle-sidebar="toggleSidebar" />

    <!-- Hero section - will be full width -->
    <div v-if="$slots.default && hasHeroSection($slots.default())" class="overflow-x-hidden">
      <div class="w-full">
        <slot name="hero" />
      </div>
    </div>

    <!-- Main content container -->
    <div class="flex">
      <!-- Sidebar -->
      <Sidebar ref="sidebar" />

      <!-- Page content -->
      <main id="main-content" class="flex-1 overflow-y-auto overflow-x-hidden p-4 md:p-8 lg:px-16 xl:px-24">
        <slot />
      </main>
    </div>
  </div>
</template>

<script setup>
// Get reference to the sidebar component
const sidebar = ref(null)

// Function to toggle sidebar
const toggleSidebar = () => {
  if (sidebar.value) {
    sidebar.value.toggleSidebar()
  }
}

// Helper function to check if the default slot contains a hero section
const hasHeroSection = (vnodes) => {
  if (!vnodes || !Array.isArray(vnodes)) return false

  for (const vnode of vnodes) {
    if (vnode.type === 'div' && Array.isArray(vnode.children)) {
      for (const child of vnode.children) {
        if (child.props && child.props.class && child.props.class.includes('h-screen')) {
          return true
        }
      }
    }
  }
  return false
}
</script>
