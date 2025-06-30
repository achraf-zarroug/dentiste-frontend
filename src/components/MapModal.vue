<template>
  <!-- Modal pour la carte en plein écran -->
  <div v-if="isOpen" class="fixed inset-0 z-50 overflow-y-auto" @click="closeModal">
    <div class="flex items-center justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
      <!-- Overlay -->
      <div class="fixed inset-0 bg-black/50 backdrop-blur-sm transition-opacity"></div>
      
      <!-- Modal content -->
      <div class="inline-block align-bottom bg-white rounded-3xl text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-4xl sm:w-full" @click.stop>
        <!-- Header -->
        <div class="bg-gradient-to-r from-teal-500 to-teal-600 px-6 py-4">
          <div class="flex items-center justify-between">
            <div class="flex items-center">
              <div class="w-10 h-10 bg-white/20 rounded-full flex items-center justify-center mr-3">
                <span class="text-white text-lg">🦷</span>
              </div>
              <div>
                <h3 class="text-lg font-bold text-white">Cabinet Dr. Chaabani</h3>
                <p class="text-teal-100 text-sm">Avenue Habib Bourguiba, Tunis</p>
              </div>
            </div>
            <button @click="closeModal" class="text-white hover:text-teal-200 transition-colors">
              <span class="text-2xl">×</span>
            </button>
          </div>
        </div>
        
        <!-- Map -->
        <div class="relative">
          <iframe
            src="https://maps.google.com/maps?q=Avenue%20Habib%20Bourguiba,%20Tunis,%20Tunisie&t=&z=16&ie=UTF8&iwloc=&output=embed"
            width="100%"
            height="400"
            style="border:0;"
            allowfullscreen=""
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"
          ></iframe>
        </div>
        
        <!-- Actions -->
        <div class="bg-gray-50 px-6 py-4">
          <div class="flex gap-4">
            <button 
              @click="openInGoogleMaps"
              class="flex-1 bg-white hover:bg-gray-100 text-gray-700 hover:text-teal-600 py-3 px-4 rounded-xl font-medium transition-all duration-300 border border-gray-200 flex items-center justify-center"
            >
              <span class="mr-2">🗺️</span>
              Ouvrir dans Google Maps
            </button>
            <button 
              @click="getDirections"
              class="flex-1 bg-teal-500 hover:bg-teal-600 text-white py-3 px-4 rounded-xl font-medium transition-all duration-300 flex items-center justify-center"
            >
              <span class="mr-2">🧭</span>
              Obtenir l'itinéraire
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  isOpen: {
    type: Boolean,
    default: false
  }
})

const emit = defineEmits(['close'])

const latitude = 36.8065
const longitude = 10.1815

const closeModal = () => {
  emit('close')
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