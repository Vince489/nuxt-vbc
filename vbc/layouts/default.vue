<template>
  <div class="min-h-screen bg-gray-900 text-white">
    <!-- Navbar -->
    <Navbar @toggle-sidebar="toggleSidebar" />

    <!-- Main content container -->
    <div class="flex">
      <!-- Sidebar -->
      <Sidebar ref="sidebar" />

      <!-- Page content -->
      <main id="main-content" class="flex-1 overflow-y-auto p-4 md:p-8 lg:px-16 xl:px-24">
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
</script>
