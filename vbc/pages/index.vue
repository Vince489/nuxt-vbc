<template>
    <div class="overflow-x-hidden">
        <!-- Hero Section -->
        <section class="relative h-screen overflow-hidden mb-12">
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
            <div class="relative z-10 container mx-auto h-full flex flex-col justify-center items-center text-center text-white">
                <!-- New content for lower left corner -->
                <div class="absolute bottom-8 left-8 text-left">
                    <p class="text-3xl font-bold mb-2">"Killer879" vs. "BoxTrot"</p>
                    <p class="text-lg mb-4">Live from Las Vegas! | July 25, 2025 - 8:00 PM EST</p>
                    <button class="px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded-lg text-lg font-medium transition-colors">
                        Pre-order PPV
                    </button>
                </div>
            </div>
        </section>

        <!-- Live Now Section -->
        <section class="section-snap fade-in-up stagger-2">
            <div class="flex items-center justify-between mb-6">
                <h2 class="text-2xl font-bold flex items-center">
                    <span class="animate-pulse w-3 h-3 bg-red-500 rounded-full mr-3"></span>
                    Live Now
                </h2>
                <span class="text-sm text-gray-400">5 active streams</span>
            </div>

            <div class="relative overflow-hidden">
                <!-- Scroll indicator container -->
                <div class="absolute bottom-0 left-0 right-0 h-1 bg-gray-200 rounded-full">
                    <!-- Active scroll indicator -->
                    <div class="h-full bg-blue-500 rounded-full" :style="{ width: indicatorWidth + '%', transform: `translateX(${indicatorPosition}px)` }"></div>
                </div>

                <!-- Navigation dots -->
                <div class="absolute bottom-8 left-0 right-0 flex justify-center space-x-2">
                    <div v-for="(card, index) in 3" :key="index"
                         class="w-2 h-2 rounded-full transition-colors"
                         :class="currentCardIndex === index ? 'bg-blue-500' : 'bg-gray-300'">
                    </div>
                </div>

                <div
                    class="flex transition-transform duration-300 ease-in-out"
                    ref="carousel"
                    @touchstart="handleTouchStart"
                    @touchmove="handleTouchMove"
                    @touchend="handleTouchEnd"
                    @mousedown="handleMouseDown"
                    @mousemove="handleMouseMove"
                    @mouseup="handleMouseUp"
                    @mouseleave="handleMouseLeave"
                >
                    <div class="flex-shrink-0 w-full md:w-1/2 lg:w-1/3 px-2">
                        <LiveCard
                            image-src="/images/jab.png"
                            title="Thunder vs Storm - Round 3"
                            description="Heavyweight Championship • Madison Square Garden"
                            viewers="2.3K"
                        />
                    </div>

                    <div class="flex-shrink-0 w-full md:w-1/2 lg:w-1/3 px-2">
                        <LiveCard
                            image-src="/images/will.png"
                            title="Lightning vs Flash - Semifinal"
                            description="Middleweight Tournament • Tokyo Arena"
                            viewers="1.8K"
                        />
                    </div>

                    <div class="flex-shrink-0 w-full md:w-1/2 lg:w-1/3 px-2">
                        <LiveCard
                            image-src="/images/lame.png"
                            title="Rookie Championship"
                            description="Amateur Division • Local Gym"
                            viewers="945"
                        />
                    </div>
                    <!-- Additional Live Cards -->
                    <div class="flex-shrink-0 w-full md:w-1/2 lg:w-1/3 px-2">
                        <LiveCard
                            image-src="/images/jab.png"
                            title="Clash of Titans - Final"
                            description="Lightweight Division • London Arena"
                            viewers="3.1K"
                        />
                    </div>
                    <div class="flex-shrink-0 w-full md:w-1/2 lg:w-1/3 px-2">
                        <LiveCard
                            image-src="/images/will.png"
                            title="Rising Stars Showcase"
                            description="Featherweight Prospects • New York City"
                            viewers="1.5K"
                        />
                    </div>
                </div>
            </div>
        </section>

        <!-- Upcoming Events Section -->
        <section class="section-snap fade-in-up stagger-2">
            <div class="flex items-center justify-between mb-6">
                <h2 class="text-2xl font-bold">Upcoming Events</h2>
            </div>

            <div class="relative overflow-hidden">
                <!-- Scroll indicator container -->
                <div class="absolute bottom-0 left-0 right-0 h-1 bg-gray-200 rounded-full">
                    <!-- Active scroll indicator -->
                    <div class="h-full bg-blue-500 rounded-full" :style="{ width: upcomingIndicatorWidth + '%', transform: `translateX(${upcomingIndicatorPosition}px)` }"></div>
                </div>

                <!-- Navigation dots -->
                <div class="absolute bottom-8 left-0 right-0 flex justify-center space-x-2">
                    <div v-for="(card, index) in 5" :key="index"
                         class="w-2 h-2 rounded-full transition-colors"
                         :class="currentCardIndex === index ? 'bg-blue-500' : 'bg-gray-300'">
                    </div>
                </div>

                <div
                    class="flex transition-transform duration-300 ease-in-out"
                    ref="upcomingCarousel"
                    @touchstart="handleUpcomingTouchStart"
                    @touchmove="handleUpcomingTouchMove"
                    @touchend="handleUpcomingTouchEnd"
                    @mousedown="handleUpcomingMouseDown"
                    @mousemove="handleUpcomingMouseMove"
                    @mouseup="handleUpcomingMouseUp"
                    @mouseleave="handleUpcomingMouseLeave"
                >
                    <div class="flex-shrink-0 w-full md:w-1/2 lg:w-1/3 px-2">
                        <PromoterEventCard
                            title="Summer Smash Fest"
                            date="Aug 20, 2025"
                            time="8:00 PM EST"
                            main-event="Main Event: Titan vs. Goliath"
                            access-type="Premium Access"
                            access-icon="fas fa-ticket-alt"
                            button-text="Set Reminder / Purchase"
                            button-color="blue"
                        />
                    </div>

                    <div class="flex-shrink-0 w-full md:w-1/2 lg:w-1/3 px-2">
                        <PromoterEventCard
                            title="Iron Fist Clash PPV"
                            date="Aug 10, 2025"
                            time="7:00 PM EST"
                            main-event="Main Event: Fighter X vs. Fighter Y"
                            access-type="Premium Access"
                            access-icon="fas fa-ticket-alt"
                            button-text="Set Reminder / Purchase"
                            button-color="blue"
                        />
                    </div>

                    <div class="flex-shrink-0 w-full md:w-1/2 lg:w-1/3 px-2">
                        <PromoterEventCard
                            title="Global Gauntlet"
                            date="Sept 01, 2025"
                            time="1:00 PM EST"
                            main-event="Featherweight Division"
                            access-type="Bracket Ready"
                            access-icon="fas fa-trophy"
                            button-text="View Details"
                            button-color="green"
                        />
                    </div>
                </div>
            </div>
        </section>

        <!-- Recent Fights Section -->
        <section class="section-snap fade-in-up stagger-2">
            <div class="flex items-center justify-between mb-6">
                <h2 class="text-2xl font-bold">Recent Fights</h2>
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
                />

                <FightCard
                    image-src="/images/will.png"
                    title="Bellator 300: Bader vs. Machida"
                    duration="2:45:00"
                    views="850K"
                    time-ago="1 week ago"
                    channel-icon="/images/logo.svg"
                    channel-name="Bellator"
                />

                <FightCard
                    image-src="/images/lame.png"
                    title="ONE Championship: Lee vs. Nguyen"
                    duration="2:30:00"
                    views="950K"
                    time-ago="3 days ago"
                    channel-icon="/images/logo.svg"
                    channel-name="ONE Championship"
                />
            </div>
        </section>

        <!-- Game Modes Section -->
        <GameModesGrid />

        <!-- News Section -->
        <NewsGrid />
    </div>
</template>

<script setup>
import { ref, onMounted, computed } from 'vue'
import NewsGrid from '@/components/NewsGrid.vue'

const carousel = ref(null)
const upcomingCarousel = ref(null)
let touchStartX = 0
let touchEndX = 0
let mouseStartX = 0
let mouseEndX = 0
let currentTranslate = 0
let isDragging = false

// Scroll indicator state for Live Now
const scrollIndicatorWidth = ref(33.33) // 100% / 3 cards
const scrollIndicatorPosition = ref(0)
const currentCardIndex = ref(0)
const cardWidth = ref(0)
const containerWidth = ref(0)

// Scroll indicator state for Upcoming Events
const upcomingScrollIndicatorWidth = ref(33.33) // 100% / 3 cards
const upcomingScrollIndicatorPosition = ref(0)
const upcomingCurrentCardIndex = ref(0)

// Computed properties for template binding
const indicatorWidth = computed(() => scrollIndicatorWidth.value)
const indicatorPosition = computed(() => scrollIndicatorPosition.value)
const upcomingIndicatorWidth = computed(() => upcomingScrollIndicatorWidth.value)
const upcomingIndicatorPosition = computed(() => upcomingScrollIndicatorPosition.value)

// Update scroll indicator and current card index
const updateScrollIndicator = () => {
  if (!carousel.value) return

  // Calculate container and card dimensions
  containerWidth.value = carousel.value.parentElement.clientWidth
  const firstCard = carousel.value.children[0]
  cardWidth.value = firstCard ? firstCard.clientWidth : containerWidth.value

  // Calculate which card is currently centered
  const absTranslate = Math.abs(currentTranslate)
  const cardPosition = absTranslate / cardWidth.value
  currentCardIndex.value = Math.round(cardPosition)

  // Calculate scroll indicator position and width
  const maxTranslate = carousel.value.scrollWidth - containerWidth.value
  const scrollPercentage = maxTranslate > 0 ? (absTranslate / maxTranslate) * 100 : 0

  // Update scroll indicator width based on visible portion
  scrollIndicatorWidth.value = (containerWidth.value / carousel.value.scrollWidth) * 100

  // Limit to container width minus indicator width to prevent going out of bounds
  const maxPosition = containerWidth.value - (containerWidth.value * (scrollIndicatorWidth.value / 100))
  scrollIndicatorPosition.value = Math.min((containerWidth.value * scrollPercentage / 100), maxPosition)
}

const handleTouchStart = (e) => {
  touchStartX = e.touches[0].clientX
  isDragging = true
  carousel.value.style.transition = 'none'
}

const handleTouchMove = (e) => {
  if (!isDragging) return
  touchEndX = e.touches[0].clientX
  const diff = touchEndX - touchStartX
  carousel.value.style.transform = `translateX(${currentTranslate + diff}px)`
}

const handleTouchEnd = () => {
  if (!isDragging) return
  isDragging = false

  const diff = touchEndX - touchStartX
  const threshold = 50 // Minimum swipe distance to trigger a slide

  if (diff > threshold) {
    // Swipe right - move to previous card
    currentTranslate = Math.min(currentTranslate + 300, 0)
  } else if (diff < -threshold) {
    // Swipe left - move to next card
    const maxTranslate = - (carousel.value.scrollWidth - carousel.value.clientWidth)
    currentTranslate = Math.max(currentTranslate - 300, maxTranslate)
  }

  carousel.value.style.transform = `translateX(${currentTranslate}px)`
  carousel.value.style.transition = 'transform 0.3s ease-in-out'

  // Update scroll indicator after animation completes
  setTimeout(updateScrollIndicator, 300)
}

// Mouse event handlers for desktop support
const handleMouseDown = (e) => {
  mouseStartX = e.clientX
  isDragging = true
  carousel.value.style.transition = 'none'
  carousel.value.style.cursor = 'grabbing'
}

const handleMouseMove = (e) => {
  if (!isDragging) return
  mouseEndX = e.clientX
  const diff = mouseEndX - mouseStartX
  carousel.value.style.transform = `translateX(${currentTranslate + diff}px)`
}

const handleMouseUp = () => {
  if (!isDragging) return
  isDragging = false
  carousel.value.style.cursor = 'grab'

  const diff = mouseEndX - mouseStartX
  const threshold = 50 // Minimum drag distance to trigger a slide

  if (diff > threshold) {
    // Drag right - move to previous card
    currentTranslate = Math.min(currentTranslate + 300, 0)
  } else if (diff < -threshold) {
    // Drag left - move to next card
    const maxTranslate = - (carousel.value.scrollWidth - carousel.value.clientWidth)
    currentTranslate = Math.max(currentTranslate - 300, maxTranslate)
  }

  carousel.value.style.transform = `translateX(${currentTranslate}px)`
  carousel.value.style.transition = 'transform 0.3s ease-in-out'

  // Update scroll indicator after animation completes
  setTimeout(updateScrollIndicator, 300)
}

const handleMouseLeave = () => {
  if (isDragging) {
    isDragging = false
    carousel.value.style.cursor = 'grab'
    carousel.value.style.transform = `translateX(${currentTranslate}px)`
    carousel.value.style.transition = 'transform 0.3s ease-in-out'

    // Update scroll indicator after animation completes
    setTimeout(updateScrollIndicator, 300)
  }
}

// Initialize carousel on mount
onMounted(() => {
  if (carousel.value) {
    carousel.value.style.cursor = 'grab'

    // Set initial values after a short delay to ensure DOM is ready
    setTimeout(updateScrollIndicator, 100)

    // Add resize observer to update on window resize
    const resizeObserver = new ResizeObserver(() => {
      updateScrollIndicator()
    })
    resizeObserver.observe(carousel.value.parentElement)
  }
})
</script>

<style scoped>
/* Additional custom styles can go here if needed */
.hero-section {
    min-height: 100vh;
}

/* Carousel container styling */
.relative.overflow-hidden {
    padding-bottom: 2rem; /* Make space for indicators */
    margin-bottom: 1rem;
}

/* Scroll indicator styling */
.absolute.bottom-0.left-0.right-0.h-1.bg-gray-200.rounded-full {
    height: 3px;
}

/* Navigation dots container */
.absolute.bottom-8.left-0.right-0.flex.justify-center.space-x-2 {
    bottom: 1.5rem;
}
</style>
