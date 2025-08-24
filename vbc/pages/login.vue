<template>
  <div class="min-h-screen flex items-center justify-center bg-gray-900">
    <div class="w-full max-w-6xl mx-auto">
      <div class="flex flex-col lg:flex-row bg-gray-800 rounded-2xl shadow-2xl overflow-hidden min-h-[600px] border border-gray-700">
        <!-- Left Panel -->
        <div class="hidden lg:flex lg:w-1/2 bg-gradient-to-br from-purple-900 via-blue-900 to-indigo-900 p-8 flex-col justify-center items-center text-white relative overflow-hidden">
          <div class="absolute inset-0 hero-pattern opacity-20"></div>
          <div class="relative z-10 text-center">
            <div class="w-24 h-24 bg-white/20 rounded-full flex items-center justify-center mb-6 mx-auto backdrop-blur-sm border border-white/30">
              <svg class="w-12 h-12 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path>
              </svg>
            </div>
            <h1 class="text-4xl font-bold mb-4 bg-gradient-to-r from-white to-gray-300 bg-clip-text text-transparent">Welcome to Aurora</h1>
            <p class="text-xl opacity-90 mb-8 text-gray-200">Experience the future of digital interaction</p>
            <div class="flex justify-center space-x-4 mb-6">
              <div class="w-3 h-3 bg-white/40 rounded-full animate-pulse"></div>
              <div class="w-3 h-3 bg-white/60 rounded-full animate-pulse animation-delay-200"></div>
              <div class="w-3 h-3 bg-white/80 rounded-full animate-pulse animation-delay-400"></div>
            </div>
            <p class="text-sm opacity-75 text-gray-300">Join thousands of users who trust Aurora</p>
          </div>
        </div>

        <!-- Right Panel -->
        <div class="w-full lg:w-1/2 p-8 lg:p-12 flex flex-col justify-center bg-gray-800">
          <div class="w-full max-w-md mx-auto">
            <!-- Tab Selector -->
            <div class="flex bg-gray-700 rounded-lg p-1 mb-8 border border-gray-600">
              <button 
                class="flex-1 py-2 px-4 text-sm font-medium rounded-md tab-button"
                :class="activeTab === 'login' ? 'active' : 'text-gray-300 hover:text-white'"
                @click="showLogin">
                Login
              </button>
              <button 
                class="flex-1 py-2 px-4 text-sm font-medium rounded-md tab-button"
                :class="activeTab === 'signup' ? 'active' : 'text-gray-300 hover:text-white'"
                @click="showSignup">
                Sign Up
              </button>
            </div>

            <!-- Login Form -->
            <div v-if="activeTab === 'login'">
              <div class="text-center mb-8">
                <h2 class="text-3xl font-bold text-white mb-2">Welcome Back</h2>
                <p class="text-gray-400">Please sign in to your account</p>
              </div>

              <form @submit.prevent="handleLogin" class="space-y-6">
                <div>
                  <label for="loginUsername" class="block text-sm font-medium text-gray-300 mb-2">Username</label>
                  <input 
                    type="text" 
                    id="loginUsername" 
                    v-model="loginUsername" 
                    class="w-full px-4 py-3 rounded-lg focus:ring-2 focus:ring-purple-500 focus:border-transparent input-focus dark-input" 
                    placeholder="Enter your username" 
                    required>
                </div>

                <div>
                  <label for="loginPassword" class="block text-sm font-medium text-gray-300 mb-2">Password</label>
                  <input 
                    type="password" 
                    id="loginPassword" 
                    v-model="loginPassword" 
                    class="w-full px-4 py-3 rounded-lg focus:ring-2 focus:ring-purple-500 focus:border-transparent input-focus dark-input" 
                    placeholder="Enter your password" 
                    required>
                </div>

                <div class="flex items-center justify-between">
                  <label class="flex items-center">
                    <input type="checkbox" v-model="rememberMe" class="w-4 h-4 text-purple-600 bg-gray-700 border-gray-600 rounded focus:ring-purple-500">
                    <span class="ml-2 text-sm text-gray-300">Remember me</span>
                  </label>
                  <NuxtLink to="/forgot-password" class="text-sm text-purple-400 hover:text-purple-300 transition-colors">Forgot password?</NuxtLink>
                </div>

                <button type="submit" class="w-full bg-gradient-to-r from-purple-600 to-blue-600 text-white py-3 px-4 rounded-lg hover:from-purple-700 hover:to-blue-700 font-medium btn-hover">
                  Sign In
                </button>
              </form>

              <div class="mt-6">
                <div class="relative">
                  <div class="absolute inset-0 flex items-center">
                    <div class="w-full border-t border-gray-600"></div>
                  </div>
                  <div class="relative flex justify-center text-sm">
                    <span class="px-2 bg-gray-800 text-gray-400">Or continue with</span>
                  </div>
                </div>

                <div class="mt-6 grid grid-cols-2 gap-3">
                  <button @click="socialLogin('google')" class="social-button flex justify-center items-center px-4 py-2 rounded-lg">
                    <svg class="w-5 h-5" viewBox="0 0 24 24">
                      <path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"></path>
                      <path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"></path>
                      <path fill="#FBBC05" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z"></path>
                      <path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z"></path>
                    </svg>
                    <span class="ml-2 text-sm font-medium text-gray-300">Google</span>
                  </button>
                  <button @click="socialLogin('twitter')" class="social-button flex justify-center items-center px-4 py-2 rounded-lg">
                    <svg class="w-5 h-5 text-gray-300" fill="currentColor" viewBox="0 0 24 24">
                      <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"></path>
                    </svg>
                    <span class="ml-2 text-sm font-medium text-gray-300">Twitter</span>
                  </button>
                </div>
              </div>
            </div>

            <!-- Sign Up Form -->
            <div v-if="activeTab === 'signup'">
              <div class="text-center mb-8">
                <h2 class="text-3xl font-bold text-white mb-2">Create Account</h2>
                <p class="text-gray-400">Join us and start your journey</p>
              </div>

              <form @submit.prevent="handleSignup" class="space-y-6">
                <div>
                  <label for="signupUsername" class="block text-sm font-medium text-gray-300 mb-2">Username</label>
                  <input 
                    type="text" 
                    id="signupUsername" 
                    v-model="signupUsername" 
                    class="w-full px-4 py-3 rounded-lg focus:ring-2 focus:ring-purple-500 focus:border-transparent input-focus dark-input" 
                    placeholder="Create a username" 
                    required>
                </div>

                <div>
                  <label for="signupPassword" class="block text-sm font-medium text-gray-300 mb-2">Password</label>
                  <input 
                    type="password" 
                    id="signupPassword" 
                    v-model="signupPassword" 
                    class="w-full px-4 py-3 rounded-lg focus:ring-2 focus:ring-purple-500 focus:border-transparent input-focus dark-input" 
                    placeholder="Create a password" 
                    required>
                </div>

                <div class="flex items-center">
                  <input type="checkbox" v-model="agreeToTerms" class="w-4 h-4 text-purple-600 bg-gray-700 border-gray-600 rounded focus:ring-purple-500" required>
                  <label class="ml-2 text-sm text-gray-300">
                    I agree to the <NuxtLink to="/terms" class="text-purple-400 hover:text-purple-300">Terms of Service</NuxtLink> and <NuxtLink to="/privacy" class="text-purple-400 hover:text-purple-300">Privacy Policy</NuxtLink>
                  </label>
                </div>

                <button type="submit" class="w-full bg-gradient-to-r from-purple-600 to-blue-600 text-white py-3 px-4 rounded-lg hover:from-purple-700 hover:to-blue-700 font-medium btn-hover">
                  Create Account
                </button>
              </form>

              <div class="mt-6">
                <div class="relative">
                  <div class="absolute inset-0 flex items-center">
                    <div class="w-full border-t border-gray-600"></div>
                  </div>
                  <div class="relative flex justify-center text-sm">
                    <span class="px-2 bg-gray-800 text-gray-400">Or sign up with</span>
                  </div>
                </div>

                <div class="mt-6 grid grid-cols-2 gap-3">
                  <button @click="socialLogin('google')" class="social-button flex justify-center items-center px-4 py-2 rounded-lg">
                    <svg class="w-5 h-5" viewBox="0 0 24 24">
                      <path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"></path>
                      <path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"></path>
                      <path fill="#FBBC05" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z"></path>
                      <path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z"></path>
                    </svg>
                    <span class="ml-2 text-sm font-medium text-gray-300">Google</span>
                  </button>
                  <button @click="socialLogin('twitter')" class="social-button flex justify-center items-center px-4 py-2 rounded-lg">
                    <svg class="w-5 h-5 text-gray-300" fill="currentColor" viewBox="0 0 24 24">
                      <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"></path>
                    </svg>
                    <span class="ml-2 text-sm font-medium text-gray-300">Twitter</span>
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Message Box Overlay -->
    <div class="message-box-overlay" :class="{ 'show': showMessageBox }"></div>
    <div class="message-box" :class="{ 'show': showMessageBox }">
      <h3 class="text-xl font-bold text-white mb-4">{{ messageBoxTitle }}</h3>
      <p class="text-gray-300 mb-6">{{ messageBoxContent }}</p>
      <button class="bg-gradient-to-r from-purple-600 to-blue-600 text-white py-2 px-4 rounded-lg hover:from-purple-700 hover:to-blue-700 transition-all duration-300" @click="hideMessageBox">Close</button>
    </div>
  </div>
</template>

<script setup>
// Meta configuration for the page
useHead({
  title: 'Aurora - Login',
  meta: [
    { name: 'description', content: 'Login to Aurora - Experience the future of digital interaction' }
  ]
})

// Reactive data
const activeTab = ref('login')
const loginUsername = ref('')
const loginPassword = ref('')
const rememberMe = ref(false)
const signupUsername = ref('')
const signupPassword = ref('')
const agreeToTerms = ref(false)
const showMessageBox = ref(false)
const messageBoxTitle = ref('')
const messageBoxContent = ref('')

// Methods
const showLogin = () => {
  activeTab.value = 'login'
}

const showSignup = () => {
  activeTab.value = 'signup'
}

const handleLogin = async () => {
  try {
    // Here you would typically call your authentication API
    // Example: await $fetch('/api/auth/login', { method: 'POST', body: { username: loginUsername.value, password: loginPassword.value } })
    
    // For demo purposes, show a message
    showMessageBoxDialog('Demo Mode', 'This is a demo. In a real app, this would authenticate the user and redirect to the dashboard.')
    
    // In a real app, you might redirect after successful login:
    // await navigateTo('/dashboard')
  } catch (error) {
    showMessageBoxDialog('Login Failed', 'Invalid username or password.')
  }
}

const handleSignup = async () => {
  try {
    // Here you would typically call your registration API
    // Example: await $fetch('/api/auth/register', { method: 'POST', body: { username: signupUsername.value, password: signupPassword.value } })
    
    // For demo purposes, show success message
    showMessageBoxDialog('Success', 'Account created successfully! Please login.')
    showLogin()
  } catch (error) {
    showMessageBoxDialog('Registration Failed', 'Unable to create account. Please try again.')
  }
}

const socialLogin = (provider) => {
  // Here you would handle OAuth login
  // Example: await $fetch(`/api/auth/${provider}`)
  showMessageBoxDialog('Social Login', `${provider} login would be handled here.`)
}

const showMessageBoxDialog = (title, message) => {
  messageBoxTitle.value = title
  messageBoxContent.value = message
  showMessageBox.value = true
}

const hideMessageBox = () => {
  showMessageBox.value = false
}

// Handle URL parameters on mount
onMounted(() => {
  const route = useRoute()
  const message = route.query.message
  
  if (message === 'error') {
    showMessageBoxDialog('Login Failed', 'Invalid username or password.')
  } else if (message === 'signup_success') {
    showMessageBoxDialog('Success', 'Account created successfully! Please login.')
    showLogin()
  }
})
</script>

<style scoped>
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes slideUp {
  from { transform: translateY(20px); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}

.animation-delay-200 {
  animation-delay: 0.2s;
}

.animation-delay-400 {
  animation-delay: 0.4s;
}

.input-focus {
  transition: all 0.3s ease;
}

.input-focus:focus {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(139, 92, 246, 0.3);
}

.btn-hover {
  transition: all 0.3s ease;
}

.btn-hover:hover {
  transform: translateY(-2px);
  box-shadow: 0 15px 35px rgba(139, 92, 246, 0.4);
}

.hero-pattern {
  background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.1'%3E%3Ccircle cx='30' cy='30' r='2'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
}

.message-box {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #1f2937;
  padding: 2rem;
  border-radius: 0.75rem;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.5);
  z-index: 1000;
  text-align: center;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
  border: 1px solid #374151;
}

.message-box.show {
  opacity: 1;
  visibility: visible;
}

.message-box-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  z-index: 999;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
}

.message-box-overlay.show {
  opacity: 1;
  visibility: visible;
}

.dark-input {
  background-color: #374151;
  border: 1px solid #4b5563;
  color: #f9fafb;
}

.dark-input:focus {
  background-color: #4b5563;
  border-color: #8b5cf6;
}

.dark-input::placeholder {
  color: #9ca3af;
}

.tab-button {
  transition: all 0.3s ease;
}

.tab-button.active {
  background: linear-gradient(135deg, #8b5cf6, #3b82f6);
  color: white;
  box-shadow: 0 4px 15px rgba(139, 92, 246, 0.3);
}

.social-button {
  background-color: #374151;
  border: 1px solid #4b5563;
  transition: all 0.3s ease;
}

.social-button:hover {
  background-color: #4b5563;
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
}
</style>