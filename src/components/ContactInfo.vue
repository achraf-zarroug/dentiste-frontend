<template>
  <div class="space-y-6">
    <div class="flex items-start group">
      <div class="flex-shrink-0 w-12 h-12 bg-gradient-to-br from-teal-400 to-teal-500 rounded-xl flex items-center justify-center mr-4 group-hover:scale-110 transition-transform">
        <span class="text-white text-lg">📍</span>
      </div>
      <div class="flex-1">
        <p class="font-semibold text-gray-800 mb-1">Adresse</p>
        <p class="text-gray-600 mb-3">
          Avenue Habib Bourguiba<br>
          Tunis, Tunisie
        </p>
        <button 
          @click="showMap = !showMap"
          class="text-teal-600 hover:text-teal-700 text-sm font-medium flex items-center transition-colors"
        >
          <span class="mr-1">🗺️</span>
          {{ showMap ? 'Masquer la carte' : 'Voir sur la carte' }}
        </button>
      </div>
    </div>

    <!-- Google Maps intégrée -->
    <div v-if="showMap" class="mt-4 rounded-2xl overflow-hidden shadow-lg border border-gray-200 animate-fadeInUp">
      <GoogleMap />
    </div>
    
    <div class="flex items-start group">
      <div class="flex-shrink-0 w-12 h-12 bg-gradient-to-br from-blue-400 to-blue-500 rounded-xl flex items-center justify-center mr-4 group-hover:scale-110 transition-transform">
        <span class="text-white text-lg">📞</span>
      </div>
      <div>
        <p class="font-semibold text-gray-800 mb-1">Téléphone</p>
        <p class="text-gray-600">
          <a href="tel:+21612345678" class="hover:text-teal-600 transition-colors">
            +216 12 345 678
          </a>
        </p>
      </div>
    </div>
    
    <div class="flex items-start group">
      <div class="flex-shrink-0 w-12 h-12 bg-gradient-to-br from-green-400 to-green-500 rounded-xl flex items-center justify-center mr-4 group-hover:scale-110 transition-transform">
        <span class="text-white text-lg">✉️</span>
      </div>
      <div>
        <p class="font-semibold text-gray-800 mb-1">Email</p>
        <p class="text-gray-600">
          <a href="mailto:dr.chaabani@email.com" class="hover:text-teal-600 transition-colors">
            dr.chaabani@email.com
          </a>
        </p>
      </div>
    </div>
    
    <div class="flex items-start group">
      <div class="flex-shrink-0 w-12 h-12 bg-gradient-to-br from-red-400 to-red-500 rounded-xl flex items-center justify-center mr-4 group-hover:scale-110 transition-transform">
        <span class="text-white text-lg">🚨</span>
      </div>
      <div>
        <p class="font-semibold text-gray-800 mb-1">Urgences</p>
        <p class="text-gray-600">
          <a href="tel:+21698765432" class="hover:text-red-600 transition-colors">
            +216 98 765 432
          </a>
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import GoogleMap from './GoogleMap.vue'

const showMap = ref(false)
</script>