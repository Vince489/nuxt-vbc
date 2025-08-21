<template>
    <div>
        <!-- Hero Section -->
        <section class="relative w-full h-screen overflow-hidden">
            <!-- Background Image -->
            <div class="absolute inset-0">
                <img
                    src="/images/banner.png"
                    alt="Hero Banner"
                    class="w-full h-full object-cover"
                />
            </div>

            <!-- Overlay for better text contrast -->
            <div class="absolute inset-0 bg-black/40"></div>

            <!-- Content -->
            <div class="relative z-10 container mx-auto px-4 h-full flex flex-col justify-center items-center text-center text-white">
                <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6">
                    Welcome to Our Platform
                </h1>
                <p class="text-xl md:text-2xl max-w-2xl mb-8">
                    Discover amazing features and services tailored just for you.
                </p>
                <button class="px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded-lg text-lg font-medium transition-colors">
                    Get Started
                </button>
            </div>
        </section>
    </div>
</template>

<script setup>
</script>

<style scoped>
/* Additional custom styles can go here if needed */
.hero-section {
    min-height: 100vh;
}
</style>
