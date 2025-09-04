<template>
  <div class="bg-gray-900 min-h-screen">
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
    <section class="bg-gray-900 p-6 md:p-8">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-white mb-6 pb-2 border-b border-gray-700 flex items-center">
          <span class="animate-pulse w-3 h-3 bg-red-600 rounded-full mr-3"></span>
          Live Now
        </h2>
        <!-- Desktop Swiper -->
        <div class="hidden md:block">
          <div class="swiper live-desktop-swiper">
            <div class="swiper-wrapper">
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/jab.png"
                  title="Championship Bout: Thunder vs Lightning"
                  description="Heavyweight title fight happening now! Don't miss it."
                  :viewers="2847"
                />
              </div>
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/will.png"
                  title="Amateur Tournament Finals"
                  description="Young fighters competing for the amateur championship."
                  :viewers="1523"
                />
              </div>
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/lame.png"
                  title="Training Session with Pro Fighters"
                  description="Watch professional fighters train and share techniques."
                  :viewers="892"
                />
              </div>
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/jab.png"
                  title="Middleweight Showdown: Fire vs Ice"
                  description="Intense middleweight battle with championship implications."
                  :viewers="1847"
                />
              </div>
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/will.png"
                  title="Women's Boxing Championship"
                  description="Elite female fighters competing for the title belt."
                  :viewers="2156"
                />
              </div>
            </div>
            <div class="swiper-button-next"></div>
            <div class="swiper-button-prev"></div>
          </div>
        </div>
        <!-- Mobile Swiper -->
        <div class="md:hidden">
          <div class="swiper live-swiper">
            <div class="swiper-wrapper">
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/jab.png"
                  title="Championship Bout: Thunder vs Lightning"
                  description="Heavyweight title fight happening now! Don't miss it."
                  :viewers="2847"
                />
              </div>
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/will.png"
                  title="Amateur Tournament Finals"
                  description="Young fighters competing for the amateur championship."
                  :viewers="1523"
                />
              </div>
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/lame.png"
                  title="Training Session with Pro Fighters"
                  description="Watch professional fighters train and share techniques."
                  :viewers="892"
                />
              </div>
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/jab.png"
                  title="Middleweight Showdown: Fire vs Ice"
                  description="Intense middleweight battle with championship implications."
                  :viewers="1847"
                />
              </div>
              <div class="swiper-slide">
                <LiveCard
                  image-src="/images/will.png"
                  title="Women's Boxing Championship"
                  description="Elite female fighters competing for the title belt."
                  :viewers="2156"
                />
              </div>
            </div>
            <div class="swiper-pagination"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Recent Fights Section -->
    <section class="bg-gray-900 p-6 md:p-8">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-white mb-6 pb-2 border-b border-gray-700 flex items-center">
          <i class="fas fa-history mr-3 text-blue-500"></i>
          Recent Fights
        </h2>
        <!-- Desktop Swiper -->
        <div class="hidden md:block">
          <div class="swiper fights-desktop-swiper">
            <div class="swiper-wrapper">
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/jab.png"
                  title="Tony Urango vs Wallup Buding"
                  duration="12:45"
                  views="15.2K"
                  time-ago="2 days ago"
                  channel-icon="/images/vbc-logo.png"
                  channel-name="Boxing Central"
                />
              </div>
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/will.png"
                  title="Mike Johnson vs Alex Rodriguez"
                  duration="8:30"
                  views="8.7K"
                  time-ago="5 days ago"
                  channel-icon="/images/viva2.png"
                  channel-name="Fight Network"
                />
              </div>
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/lame.png"
                  title="Sarah Williams vs Emma Davis"
                  duration="10:15"
                  views="12.1K"
                  time-ago="1 week ago"
                  channel-icon="/images/viva2.png"
                  channel-name="Women's Boxing"
                />
              </div>
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/jab.png"
                  title="Championship Final: Smith vs Jones"
                  duration="15:20"
                  views="25.8K"
                  time-ago="2 weeks ago"
                  channel-icon="/images/vbc-logo.png"
                  channel-name="Boxing Central"
                />
              </div>
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/will.png"
                  title="Heavyweight Clash: Thompson vs Wilson"
                  duration="11:30"
                  views="18.9K"
                  time-ago="1 month ago"
                  channel-icon="/images/viva2.png"
                  channel-name="Fight Network"
                />
              </div>
            </div>
            <div class="swiper-button-next"></div>
            <div class="swiper-button-prev"></div>
          </div>
        </div>
        <!-- Mobile Swiper -->
        <div class="md:hidden">
          <div class="swiper fights-swiper">
            <div class="swiper-wrapper">
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/jab.png"
                  title="Tony Urango vs Wallup Buding"
                  duration="12:45"
                  views="15.2K"
                  time-ago="2 days ago"
                  channel-icon="/images/vbc-logo.png"
                  channel-name="Boxing Central"
                />
              </div>
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/will.png"
                  title="Mike Johnson vs Alex Rodriguez"
                  duration="8:30"
                  views="8.7K"
                  time-ago="5 days ago"
                  channel-icon="/images/viva2.png"
                  channel-name="Fight Network"
                />
              </div>
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/lame.png"
                  title="Sarah Williams vs Emma Davis"
                  duration="10:15"
                  views="12.1K"
                  time-ago="1 week ago"
                  channel-icon="/images/viva2.png"
                  channel-name="Women's Boxing"
                />
              </div>
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/jab.png"
                  title="Championship Final: Smith vs Jones"
                  duration="15:20"
                  views="25.8K"
                  time-ago="2 weeks ago"
                  channel-icon="/images/vbc-logo.png"
                  channel-name="Boxing Central"
                />
              </div>
              <div class="swiper-slide">
                <FightCard
                  image-src="/images/will.png"
                  title="Heavyweight Clash: Thompson vs Wilson"
                  duration="11:30"
                  views="18.9K"
                  time-ago="1 month ago"
                  channel-icon="/images/viva2.png"
                  channel-name="Fight Network"
                />
              </div>
            </div>
            <div class="swiper-pagination"></div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import Swiper from 'swiper'
import { Navigation, Pagination } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/navigation'
import 'swiper/css/pagination'

const sidebarRef = ref(null);

const toggleSidebar = () => {
  sidebarRef.value?.toggleSidebar();
};

onMounted(() => {
  // Initialize Live Desktop Swiper
  new Swiper('.live-desktop-swiper', {
    modules: [Navigation, Pagination],
    slidesPerView: 3,
    spaceBetween: 24,
    navigation: {
      nextEl: '.live-desktop-swiper .swiper-button-next',
      prevEl: '.live-desktop-swiper .swiper-button-prev',
    },
    breakpoints: {
      768: {
        slidesPerView: 2,
        spaceBetween: 20,
      },
      1024: {
        slidesPerView: 3,
        spaceBetween: 24,
      },
    },
  });

  // Initialize Fights Desktop Swiper
  new Swiper('.fights-desktop-swiper', {
    modules: [Navigation, Pagination],
    slidesPerView: 3,
    spaceBetween: 24,
    navigation: {
      nextEl: '.fights-desktop-swiper .swiper-button-next',
      prevEl: '.fights-desktop-swiper .swiper-button-prev',
    },
    breakpoints: {
      768: {
        slidesPerView: 2,
        spaceBetween: 20,
      },
      1024: {
        slidesPerView: 3,
        spaceBetween: 24,
      },
    },
  });

  // Initialize Live Mobile Swiper
  new Swiper('.live-swiper', {
    modules: [Navigation, Pagination],
    slidesPerView: 1,
    spaceBetween: 20,
    pagination: {
      el: '.live-swiper .swiper-pagination',
      clickable: true,
    },
    breakpoints: {
      640: {
        slidesPerView: 1.5,
        spaceBetween: 20,
      },
    },
  });

  // Initialize Fights Mobile Swiper
  new Swiper('.fights-swiper', {
    modules: [Navigation, Pagination],
    slidesPerView: 1,
    spaceBetween: 20,
    pagination: {
      el: '.fights-swiper .swiper-pagination',
      clickable: true,
    },
    breakpoints: {
      640: {
        slidesPerView: 1.5,
        spaceBetween: 20,
      },
    },
  });
});
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

/* Swiper Styles */
.swiper {
  width: 100%;
  height: 100%;
  padding-bottom: 40px;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  background: transparent;
  display: flex;
  justify-content: center;
  align-items: center;
}

.swiper-pagination {
  bottom: 0 !important;
}

.swiper-pagination-bullet {
  background: #6b7280;
  opacity: 0.5;
}

.swiper-pagination-bullet-active {
  background: #3b82f6;
  opacity: 1;
}

/* Navigation arrows */
.swiper-button-next,
.swiper-button-prev {
  color: #3b82f6;
  background: rgba(0, 0, 0, 0.5);
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin-top: -20px;
}

.swiper-button-next:after,
.swiper-button-prev:after {
  font-size: 16px;
  font-weight: bold;
}

.swiper-button-next:hover,
.swiper-button-prev:hover {
  background: rgba(0, 0, 0, 0.7);
  color: #60a5fa;
}

/* Mobile specific adjustments */
@media (max-width: 768px) {
  .swiper-slide {
    width: auto;
  }
}
</style>
