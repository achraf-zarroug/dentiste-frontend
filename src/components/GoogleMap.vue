<template>
  <div class="relative">
    <!-- Google Maps Embed -->
    <div class="w-full h-64 bg-gray-100 rounded-lg overflow-hidden relative">
      <iframe
        :src="mapUrl"
        width="100%"
        height="100%"
        style="border:0;"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        class="rounded-lg"
      ></iframe>
      
      <!-- Overlay avec informations -->
      <div class="absolute top-4 left-4 bg-white/95 backdrop-blur-sm p-3 rounded-lg shadow-lg border border-gray-200">
        <div class="flex items-center">
          <div class="w-8 h-8 bg-gradient-to-br from-teal-400 to-teal-500 rounded-full flex items-center justify-center mr-3">
            <span class="text-white text-sm">🦷</span>
          </div>
          <div>
            <p class="font-semibold text-gray-800 text-sm">Dr. Chaabani</p>
            <p class="text-gray-600 text-xs">Cabinet Dentaire</p>
          </div>
        </div>
      </div>
      
      <!-- Boutons d'action -->
      <div class="absolute bottom-4 right-4 flex gap-2">
        <button 
          @click="openInGoogleMaps"
          class="bg-white/95 backdrop-blur-sm hover:bg-white text-gray-700 hover:text-teal-600 p-2 rounded-lg shadow-lg border border-gray-200 transition-all duration-300 group"
          title="Ouvrir dans Google Maps"
        >
          <span class="text-lg group-hover:scale-110 transition-transform inline-block">🗺️</span>
        </button>
        <button 
          @click="getDirections"
          class="bg-white/95 backdrop-blur-sm hover:bg-white text-gray-700 hover:text-blue-600 p-2 rounded-lg shadow-lg border border-gray-200 transition-all duration-300 group"
          title="Obtenir l'itinéraire"
        >
          <span class="text-lg group-hover:scale-110 transition-transform inline-block">🧭</span>
        </button>
      </div>
    </div>
    
    <!-- Informations supplémentaires -->
    <div class="mt-4 grid grid-cols-2 gap-4">
      <div class="bg-gradient-to-br from-teal-50 to-blue-50 p-4 rounded-xl">
        <div class="flex items-center mb-2">
          <span class="text-teal-600 mr-2">🚗</span>
          <span class="font-semibold text-gray-800 text-sm">Parking</span>
        </div>
        <p class="text-gray-600 text-xs">Parking gratuit disponible</p>
      </div>
      <div class="bg-gradient-to-br from-green-50 to-teal-50 p-4 rounded-xl">
        <div class="flex items-center mb-2">
          <span class="text-green-600 mr-2">🚌</span>
          <span class="font-semibold text-gray-800 text-sm">Transport</span>
        </div>
        <p class="text-gray-600 text-xs">Accessible en transport public</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

// Coordonnées du cabinet (exemple pour Tunis)
const latitude = 36.8065
const longitude = 10.1815
const address = "Avenue Habib Bourguiba, Tunis, Tunisie"

// URL pour l'embed Google Maps
const mapUrl = computed(() => {
  const encodedAddress = encodeURIComponent(address)
  return `https://www.google.com/maps/embed/v1/place?key=YOUR_API_KEY&q=${encodedAddress}&zoom=15&maptype=roadmap`
})

// Alternative sans API key (utilise Google Maps standard)
const mapUrlNoKey = computed(() => {
  const encodedAddress = encodeURIComponent(address)
  return `https://maps.google.com/maps?q=${encodedAddress}&t=&z=15&ie=UTF8&iwloc=&output=embed`
})

const openInGoogleMaps = () => {
  const url = `https://www.google.com/maps/search/?api=1&query=${latitude},${longitude}`
  window.open(url, '_blank')
}

const getDirections = () => {
  const url = `https://www.google.com/maps/dir/?api=1&destination=${latitude},${longitude}`
  window.open(url, '_blank')
}
</script>