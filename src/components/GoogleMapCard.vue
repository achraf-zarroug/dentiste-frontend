<template>
  <div class="bg-gradient-to-br from-gray-50 to-gray-100 rounded-2xl p-4 border border-gray-200">
    <!-- Carte miniature -->
    <div class="relative w-full h-48 bg-gray-200 rounded-xl overflow-hidden mb-4 group cursor-pointer" @click="openFullMap">
      <iframe
        src="https://maps.google.com/maps?q=Avenue%20Habib%20Bourguiba,%20Tunis,%20Tunisie&t=&z=15&ie=UTF8&iwloc=&output=embed"
        width="100%"
        height="100%"
        style="border:0;"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        class="rounded-xl transition-all duration-300 group-hover:scale-105"
      ></iframe>
      
      <!-- Overlay hover -->
      <div class="absolute inset-0 bg-black/0 group-hover:bg-black/10 transition-all duration-300 flex items-center justify-center">
        <div class="opacity-0 group-hover:opacity-100 transition-all duration-300 bg-white/90 backdrop-blur-sm px-4 py-2 rounded-full">
          <span class="text-gray-800 font-medium text-sm">Cliquer pour agrandir</span>
        </div>
      </div>
    </div>
    
    <!-- Actions rapides -->
    <div class="flex gap-3">
      <button 
        @click="openInGoogleMaps"
        class="flex-1 bg-white hover:bg-gray-50 text-gray-700 hover:text-teal-600 py-3 px-4 rounded-xl text-sm font-medium transition-all duration-300 border border-gray-200 flex items-center justify-center"
      >
        <span class="mr-2">🗺️</span>
        Ouvrir Maps
      </button>
      <button 
        @click="getDirections"
        class="flex-1 bg-teal-500 hover:bg-teal-600 text-white py-3 px-4 rounded-xl text-sm font-medium transition-all duration-300 flex items-center justify-center"
      >
        <span class="mr-2">🧭</span>
        Itinéraire
      </button>
    </div>
    
    <!-- Informations pratiques -->
    <div class="mt-4 grid grid-cols-2 gap-3">
      <div class="text-center p-3 bg-white/50 rounded-lg">
        <div class="text-lg mb-1">🚗</div>
        <div class="text-xs text-gray-600">Parking gratuit</div>
      </div>
      <div class="text-center p-3 bg-white/50 rounded-lg">
        <div class="text-lg mb-1">🚌</div>
        <div class="text-xs text-gray-600">Transport public</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const showFullMap = ref(false)

// Coordonnées du cabinet
const latitude = 36.8065
const longitude = 10.1815

const openFullMap = () => {
  showFullMap.value = true
}

const openInGoogleMaps = () => {
  const url = `https://www.google.com/maps/search/?api=1&query=${latitude},${longitude}`
  window.open(url, '_blank')
}

const getDirections = () => {
  const url = `https://www.google.com/maps/dir/?api=1&destination=${latitude},${longitude}`
  window.open(url, '_blank')
}
</script>