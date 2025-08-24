<template>
    <nav id="main-header" class="fixed top-0 left-0 right-0 bg-gray-800 px-4 py-3 flex items-center justify-between z-50">
        <div class="flex items-center space-x-4">
            <button @click="$emit('toggle-sidebar')" class="text-gray-400 hover:text-white focus:outline-none">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                </svg>
            </button>
            <NuxtLink to="/">
                <img src="/images/logo.svg" alt="Virtron Logo" class="h-6">
            </NuxtLink>
        </div>

        <div class="flex items-center space-x-3">
            <!-- Log In Button -->
            <button class="bg-gray-700 text-gray-200 hover:bg-gray-600 focus:outline-none py-1.5 px-5 rounded-lg font-semibold text-sm transition-colors">
                Log in
            </button>
            <!-- Sign Up Button -->
            <button class="bg-white text-gray-900 hover:bg-gray-200 focus:outline-none py-1.5 px-5 rounded-lg font-semibold text-sm transition-colors">
                Sign up
            </button>
        </div>
    </nav>
</template>
