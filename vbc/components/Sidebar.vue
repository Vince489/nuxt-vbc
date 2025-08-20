<template>
    <div class="sidebar-container">
        <div id="sidebar" class="fixed left-0 top-12 h-[calc(100vh-3rem)] w-64 bg-gray-800 shadow-lg transform -translate-x-full sidebar-transition z-40 border-r border-gray-700">
            <div class="p-4 h-full overflow-y-auto">
                <div id="sidebar-content">
                    <nav class="space-y-2">
                        <NuxtLink to="/" class="flex items-center p-3 rounded-lg bg-gray-700 text-gray-300">
                            <Icon name="uil:home" class="mr-3 w-6 text-center" />
                            <span>Home</span>
                        </NuxtLink>
                        <NuxtLink to="/rules" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:compass" class="mr-3 w-6 text-center" />
                            <span>Rules</span>
                        </NuxtLink>
                        <NuxtLink to="/shorts" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:play-circle" class="mr-3 w-6 text-center" />
                            <span>Shorts</span>
                        </NuxtLink>
                        <NuxtLink to="/my-fighters" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="heroicons:tv" class="mr-3 w-6 text-center" />
                            <span>My Fighters</span>
                        </NuxtLink>
                    </nav>

                    <hr class="my-3 border-gray-700">

                    <nav class="space-y-2">
                        <NuxtLink to="/library" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:video" class="mr-3 w-6 text-center" />
                            <span>Library</span>
                        </NuxtLink>
                        <NuxtLink to="/history" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:history" class="mr-3 w-6 text-center" />
                            <span>History</span>
                        </NuxtLink>
                        <NuxtLink to="/watch-later" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:clock" class="mr-3 w-6 text-center" />
                            <span>Watch Later</span>
                        </NuxtLink>
                        <NuxtLink to="/liked-videos" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:thumbs-up" class="mr-3 w-6 text-center" />
                            <span>Liked Videos</span>
                        </NuxtLink>
                        <NuxtLink to="/ppv" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:ticket" class="mr-3 w-6 text-center" />
                            <span>PPV Events</span>
                        </NuxtLink>
                    </nav>

                    <hr class="my-3 border-gray-700">

                    <h3 class="px-3 mb-1 text-sm font-medium text-gray-400">SUBSCRIPTIONS</h3>
                    <nav class="space-y-2 mt-2">
                        <NuxtLink to="#" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <div class="w-6 h-6 rounded-full bg-red-500 flex items-center justify-center mr-3">F</div>
                            <span>Fight Hype</span>
                        </NuxtLink>
                        <NuxtLink to="#" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <div class="w-6 h-6 rounded-full bg-blue-500 flex items-center justify-center mr-3">P</div>
                            <span>Promoters</span>
                        </NuxtLink>
                        <NuxtLink to="#" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <div class="w-6 h-6 rounded-full bg-green-500 flex items-center justify-center mr-3">E</div>
                            <span>EAC</span>
                        </NuxtLink>
                        <NuxtLink to="#" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <div class="w-6 h-6 rounded-full bg-yellow-500 flex items-center justify-center mr-3">F</div>
                            <span>FytRec 2</span>
                        </NuxtLink>
                    </nav>

                    <hr class="my-3 border-gray-700">

                    <h3 class="px-3 mb-1 text-sm font-medium text-gray-400">EXPLORE</h3>
                    <nav class="space-y-2 mt-2">
                        <NuxtLink to="#" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:chart-line" class="mr-3 w-6 text-center" />
                            <span>Trending</span>
                        </NuxtLink>
                        <NuxtLink to="#" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:music" class="mr-3 w-6 text-center" />
                            <span>Music</span>
                        </NuxtLink>
                        <NuxtLink to="#" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="heroicons:device-phone-mobile" class="mr-3 w-6 text-center" />
                            <span>Gaming</span>
                        </NuxtLink>
                        <NuxtLink to="#" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:newspaper" class="mr-3 w-6 text-center" />
                            <span>News</span>
                        </NuxtLink>
                        <NuxtLink to="#" class="flex items-center p-3 rounded-lg hover:bg-gray-700 text-gray-300">
                            <Icon name="uil:baseball-ball" class="mr-3 w-6 text-center" />
                            <span>Sports</span>
                        </NuxtLink>
                    </nav>

                    <hr class="my-3 border-gray-700">

                    <div class="py-3 px-3 text-xs text-gray-400">
                        <div class="flex flex-wrap gap-2 mb-3">
                            <NuxtLink to="#" class="hover:text-gray-200">About</NuxtLink>
                            <NuxtLink to="#" class="hover:text-gray-200">Press</NuxtLink>
                            <NuxtLink to="#" class="hover:text-gray-200">Copyright</NuxtLink>
                            <NuxtLink to="#" class="hover:text-gray-200">Contact</NuxtLink>
                            <NuxtLink to="#" class="hover:text-gray-200">Creators</NuxtLink>
                            <NuxtLink to="#" class="hover:text-gray-200">Advertise</NuxtLink>
                        </div>
                        <div class="flex flex-wrap gap-2 mb-3">
                            <NuxtLink to="#" class="hover:text-gray-200">Terms</NuxtLink>
                            <NuxtLink to="#" class="hover:text-gray-200">Privacy</NuxtLink>
                            <NuxtLink to="#" class="hover:text-gray-200">Policy & Safety</NuxtLink>
                            <NuxtLink to="#" class="hover:text-gray-200">How VBC works</NuxtLink>
                            <NuxtLink to="#" class="hover:text-gray-200">Test new features</NuxtLink>
                        </div>
                        <p class="mt-4">© 2023 Virtron LLC</p>
                    </div>
                </div>
            </div>
        </div>

        <div id="overlay" class="fixed inset-0 bg-black bg-opacity-50 z-30 hidden" @click="closeSidebar"></div>
    </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const sidebarOpen = ref(false)

const toggleSidebar = () => {
    sidebarOpen.value = !sidebarOpen.value
    const sidebar = document.getElementById('sidebar')
    const overlay = document.getElementById('overlay')

    if (sidebarOpen.value) {
        sidebar.classList.remove('-translate-x-full')
        overlay.classList.remove('hidden')
    } else {
        sidebar.classList.add('-translate-x-full')
        overlay.classList.add('hidden')
    }
}

const closeSidebar = () => {
    sidebarOpen.value = false
    const sidebar = document.getElementById('sidebar')
    const overlay = document.getElementById('overlay')

    sidebar.classList.add('-translate-x-full')
    overlay.classList.add('hidden')
}

// Close sidebar when clicking outside on larger screens
const handleClickOutside = (event) => {
    const sidebar = document.getElementById('sidebar')
    const menuButton = event.target.closest('button')

    if (sidebarOpen.value && !sidebar.contains(event.target) && !menuButton) {
        closeSidebar()
    }
}

// Close sidebar on escape key
const handleKeyDown = (event) => {
    if (event.key === 'Escape' && sidebarOpen.value) {
        closeSidebar()
    }
}

onMounted(() => {
    // Add event listeners
    document.addEventListener('click', handleClickOutside)
    document.addEventListener('keydown', handleKeyDown)
})

onUnmounted(() => {
    // Remove event listeners when component is unmounted
    document.removeEventListener('click', handleClickOutside)
    document.removeEventListener('keydown', handleKeyDown)
})

// Expose the toggleSidebar function to be used by parent components
defineExpose({
    toggleSidebar,
    closeSidebar
})
</script>

<style scoped>
.sidebar-transition {
    transition: transform 0.3s ease-in-out;
}

/* Custom scrollbar for dark theme */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-track {
    background: #2d3748;
}

::-webkit-scrollbar-thumb {
    background: #4a5568;
    border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
    background: #718096;
}
</style>
