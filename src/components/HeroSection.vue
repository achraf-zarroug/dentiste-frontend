<template>
  <section id="home" class="relative py-20 lg:py-32 overflow-hidden">
    <!-- Éléments décoratifs supplémentaires -->
    <div class="absolute top-20 left-1/4 w-32 h-32 bg-teal-100 rounded-full opacity-20 animate-float"></div>
    <div class="absolute bottom-20 right-1/4 w-24 h-24 bg-yellow-100 rounded-full opacity-30 animate-float" style="animation-delay: 1s;"></div>
    
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
      <div class="text-center">
        <!-- Logo central avec animation -->
        <div class="mb-12 flex justify-center">
          <div class="relative">
            <div class="w-32 h-32 bg-gradient-to-br from-white to-gray-50 rounded-full shadow-2xl flex items-center justify-center border border-gray-100">
              <div class="w-20 h-20 bg-gradient-to-br from-teal-400 to-teal-500 rounded-full flex items-center justify-center">
                <div class="text-white text-3xl">🦷</div>
              </div>
            </div>
            <div class="absolute -top-2 -right-2 w-8 h-8 bg-yellow-400 rounded-full animate-bounce"></div>
            <div class="absolute -bottom-2 -left-2 w-6 h-6 bg-pink-400 rounded-full animate-pulse"></div>
          </div>
        </div>
        
        <div class="max-w-4xl mx-auto">
          <h1 class="text-5xl md:text-6xl lg:text-7xl font-bold mb-8 animate-fadeInUp">
            <span class="bg-gradient-to-r from-gray-800 via-gray-700 to-gray-800 bg-clip-text text-transparent">
              Dr. Achraf Zarroug
            </span>
          </h1>
          
          <p class="text-xl md:text-2xl text-gray-600 mb-4 animate-fadeInUp" style="animation-delay: 0.2s;">
            Chirurgien Dentiste
          </p>
          
          <p class="text-lg text-gray-500 mb-12 max-w-2xl mx-auto leading-relaxed animate-fadeInUp" style="animation-delay: 0.4s;">
            Des soins dentaires d'excellence dans un environnement moderne et bienveillant. 
            Votre sourire est notre priorité absolue.
          </p>
          
          <div class="flex flex-col sm:flex-row gap-6 justify-center items-center animate-fadeInUp" style="animation-delay: 0.6s;">
            <button 
              @click="scrollToContact"
              class="group bg-gradient-to-r from-teal-500 to-teal-600 hover:from-teal-600 hover:to-teal-700 text-white px-8 py-4 rounded-full text-lg font-medium transition-all duration-300 shadow-lg hover:shadow-xl transform hover:-translate-y-1 flex items-center"
            >
              <span class="mr-3 text-xl">📅</span>
              Prendre rendez-vous
              <span class="ml-2 group-hover:translate-x-1 transition-transform">→</span>
            </button>
            
            <button 
              @click="callPhone"
              class="group border-2 border-teal-500 text-teal-600 hover:bg-teal-500 hover:text-white px-8 py-4 rounded-full text-lg font-medium transition-all duration-300 flex items-center"
            >
              <span class="mr-3 text-xl">📞</span>
              Nous appeler
            </button>
          </div>
        </div>
        
        <!-- Statistiques -->
        <div class="mt-20 grid grid-cols-2 md:grid-cols-4 gap-8 max-w-4xl mx-auto">
          <div class="text-center animate-fadeInUp" style="animation-delay: 0.8s;">
            <div class="text-3xl font-bold text-teal-600 mb-2">15+</div>
            <div class="text-sm text-gray-500">Années d'expérience</div>
          </div>
          <div class="text-center animate-fadeInUp" style="animation-delay: 1s;">
            <div class="text-3xl font-bold text-teal-600 mb-2">2000+</div>
            <div class="text-sm text-gray-500">Patients satisfaits</div>
          </div>
          <div class="text-center animate-fadeInUp" style="animation-delay: 1.2s;">
            <div class="text-3xl font-bold text-teal-600 mb-2">98%</div>
            <div class="text-sm text-gray-500">Taux de satisfaction</div>
          </div>
          <div class="text-center animate-fadeInUp" style="animation-delay: 1.4s;">
            <div class="text-3xl font-bold text-teal-600 mb-2">24/7</div>
            <div class="text-sm text-gray-500">Urgences</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const scrollToContact = () => {
  document.getElementById('contact')?.scrollIntoView({ behavior: 'smooth' })
}

const callPhone = () => {
  window.location.href = 'tel:+21612345678'
}
</script>