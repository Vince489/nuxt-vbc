<template>
    <div>
        <!-- Hero Section -->
        <section class="relative w-full h-screen overflow-hidden mb-12">
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
<!-- Live Now Section -->
            <section class="section-snap fade-in-up stagger-2">
                <div class="flex items-center justify-between mb-6">
                    <h2 class="text-2xl font-bold flex items-center">
                        <span class="animate-pulse w-3 h-3 bg-red-500 rounded-full mr-3"></span>
                        Live Now
                    </h2>
                    <span class="text-sm text-gray-400">3 active streams</span>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <LiveCard
                        image-src="/images/jab.png"
                        title="Thunder vs Storm - Round 3"
                        description="Heavyweight Championship • Madison Square Garden"
                        viewers="2.3K"
                    />

                    <LiveCard
                        image-src="/images/will.png"
                        title="Lightning vs Flash - Semifinal"
                        description="Middleweight Tournament • Tokyo Arena"
                        viewers="1.8K"
                    />

                    <LiveCard
                        image-src="/images/lame.png"
                        title="Rookie Championship"
                        description="Amateur Division • Local Gym"
                        viewers="945"
                    />
                </div>
            </section>

            <!-- Upcoming Fights Section -->
            <section class="section-snap fade-in-up stagger-2">
                <div class="flex items-center justify-between mb-6">
                    <h2 class="text-2xl font-bold">Upcoming Fights</h2>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <FightCard
                        image-src="/images/jab.png"
                        title="UFC 290: Volkanovski vs. Rodriguez"
                        duration="3:00:00"
                        views="1.2M"
                        time-ago="2 days ago"
                        channel-icon="/images/logo.svg"
                        channel-name="UFC"
                        fighter1="Alexander Volkanovski"
                        fighter2="Yair Rodriguez"
                        weight-class="Featherweight"
                        event-name="UFC 290"
                    />

                    <FightCard
                        image-src="/images/will.png"
                        title="Bellator 300: Bader vs. Machida"
                        duration="2:45:00"
                        views="850K"
                        time-ago="1 week ago"
                        channel-icon="/images/logo.svg"
                        channel-name="Bellator"
                        fighter1="Ryan Bader"
                        fighter2="Lyoto Machida"
                        weight-class="Light Heavyweight"
                        event-name="Bellator 300"
                    />

                    <FightCard
                        image-src="/images/lame.png"
                        title="ONE Championship: Lee vs. Nguyen"
                        duration="2:30:00"
                        views="950K"
                        time-ago="3 days ago"
                        channel-icon="/images/logo.svg"
                        channel-name="ONE Championship"
                        fighter1="Christian Lee"
                        fighter2="Thanh Le"
                        weight-class="Lightweight"
                        event-name="ONE 168"
                    />
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
