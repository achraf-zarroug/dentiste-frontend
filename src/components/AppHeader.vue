<template>
  <header class="bg-white/80 backdrop-blur-md shadow-sm sticky top-0 z-50 border-b border-gray-100">
    <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center py-4">
        <div class="flex items-center">
          <router-link to="/" class="flex-shrink-0 flex items-center group">
            <div class="relative">
              <div class="h-12 w-12 bg-gradient-to-br from-teal-400 to-teal-500 rounded-full flex items-center justify-center shadow-lg group-hover:shadow-xl transition-all duration-300">
                <div class="text-white text-xl">🦷</div>
              </div>
              <div class="absolute -top-1 -right-1 w-4 h-4 bg-yellow-400 rounded-full animate-pulse"></div>
            </div>
            <div class="ml-3">
              <span class="text-2xl font-bold bg-gradient-to-r from-gray-800 to-gray-600 bg-clip-text text-transparent">
                Dr. Zarroug
              </span>
              <p class="text-sm text-gray-500 -mt-1">Chirurgien Dentiste</p>
            </div>
          </router-link>
        </div>
        
        <div class="hidden md:block">
          <div class="ml-10 flex items-baseline space-x-8">
            <a href="#home" class="text-gray-700 hover:text-teal-600 px-3 py-2 text-sm font-medium transition-all duration-300 relative group">
              Accueil
              <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-teal-500 group-hover:w-full transition-all duration-300"></span>
            </a>
            <a href="#services" class="text-gray-700 hover:text-teal-600 px-3 py-2 text-sm font-medium transition-all duration-300 relative group">
              Services
              <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-teal-500 group-hover:w-full transition-all duration-300"></span>
            </a>
            <a href="#about" class="text-gray-700 hover:text-teal-600 px-3 py-2 text-sm font-medium transition-all duration-300 relative group">
              À propos
              <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-teal-500 group-hover:w-full transition-all duration-300"></span>
            </a>
            <a href="#contact" class="text-gray-700 hover:text-teal-600 px-3 py-2 text-sm font-medium transition-all duration-300 relative group">
              Contact
              <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-teal-500 group-hover:w-full transition-all duration-300"></span>
            </a>
          </div>
        </div>
        
        <div class="hidden md:block">
          <button 
            @click="openAppointmentModal"
            class="bg-gradient-to-r from-teal-500 to-teal-600 hover:from-teal-600 hover:to-teal-700 text-white px-6 py-2.5 rounded-full text-sm font-medium transition-all duration-300 shadow-lg hover:shadow-xl transform hover:-translate-y-0.5"
          >
            Prendre RDV
          </button>
        </div>
        
        <div class="md:hidden">
          <button @click="mobileMenuOpen = !mobileMenuOpen" class="text-gray-700 hover:text-teal-600 transition-colors">
            <div class="w-6 h-6 flex flex-col justify-center items-center">
              <span class="block w-5 h-0.5 bg-current mb-1 transition-all" :class="{ 'rotate-45 translate-y-1.5': mobileMenuOpen }"></span>
              <span class="block w-5 h-0.5 bg-current mb-1 transition-all" :class="{ 'opacity-0': mobileMenuOpen }"></span>
              <span class="block w-5 h-0.5 bg-current transition-all" :class="{ '-rotate-45 -translate-y-1.5': mobileMenuOpen }"></span>
            </div>
          </button>
        </div>
      </div>
      
      <!-- Mobile menu -->
      <div v-if="mobileMenuOpen" class="md:hidden">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3 bg-white/95 backdrop-blur-md border-t border-gray-100 rounded-b-lg">
          <a href="#home" class="text-gray-700 hover:text-teal-600 block px-3 py-2 text-base font-medium transition-colors">Accueil</a>
          <a href="#services" class="text-gray-700 hover:text-teal-600 block px-3 py-2 text-base font-medium transition-colors">Services</a>
          <a href="#about" class="text-gray-700 hover:text-teal-600 block px-3 py-2 text-base font-medium transition-colors">À propos</a>
          <a href="#contact" class="text-gray-700 hover:text-teal-600 block px-3 py-2 text-base font-medium transition-colors">Contact</a>
          <button 
            @click="openAppointmentModal"
            class="w-full text-left bg-gradient-to-r from-teal-500 to-teal-600 text-white px-3 py-2 rounded-full text-base font-medium mt-2 transition-all"
          >
            Prendre RDV
          </button>
        </div>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const mobileMenuOpen = ref(false)

const openAppointmentModal = () => {
  console.log('Ouvrir modal de rendez-vous')
}
</script>