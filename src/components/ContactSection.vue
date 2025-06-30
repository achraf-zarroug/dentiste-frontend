<template>
  <section id="contact" class="py-20 relative overflow-hidden">
    <!-- Fond avec dégradé -->
    <div class="absolute inset-0 bg-gradient-to-br from-teal-50 via-white to-blue-50"></div>
    
    <!-- Éléments décoratifs -->
    <div class="absolute top-10 left-10 w-20 h-20 bg-teal-100 rounded-full opacity-30 animate-float"></div>
    <div class="absolute bottom-10 right-10 w-16 h-16 bg-yellow-100 rounded-full opacity-40 animate-float" style="animation-delay: 2s;"></div>
    
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
      <div class="text-center mb-16">
        <div class="inline-flex items-center px-4 py-2 bg-teal-50 rounded-full text-teal-600 text-sm font-medium mb-4">
          <span class="mr-2">📞</span>
          Contact
        </div>
        <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-6">
          Prenez rendez-vous
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Notre équipe est à votre disposition pour répondre à vos questions 
          et planifier votre consultation.
        </p>
      </div>
      
      <div class="lg:grid lg:grid-cols-2 lg:gap-16 items-start">
        <div class="mb-12 lg:mb-0">
          <div class="bg-white/80 backdrop-blur-sm p-8 rounded-3xl shadow-xl border border-gray-100">
            <h3 class="text-2xl font-bold text-gray-800 mb-8">Informations de contact</h3>
            <ContactInfo />
            
            <!-- Horaires -->
            <div class="mt-8 p-6 bg-gradient-to-br from-teal-50 to-blue-50 rounded-2xl">
              <h4 class="font-bold text-gray-800 mb-4 flex items-center">
                <span class="mr-2">🕒</span>
                Horaires d'ouverture
              </h4>
              <div class="space-y-2 text-gray-600">
                <div class="flex justify-between">
                  <span>Lundi - Vendredi</span>
                  <span class="font-medium">8h00 - 18h00</span>
                </div>
                <div class="flex justify-between">
                  <span>Samedi</span>
                  <span class="font-medium">8h00 - 14h00</span>
                </div>
                <div class="flex justify-between">
                  <span>Dimanche</span>
                  <span class="font-medium text-red-500">Fermé</span>
                </div>
              </div>
            </div>

            <!-- Section Google Maps dédiée -->
            <div class="mt-8">
              <h4 class="font-bold text-gray-800 mb-4 flex items-center">
                <span class="mr-2">🗺️</span>
                Localisation
              </h4>
              <GoogleMapCard />
            </div>
          </div>
        </div>
        
        <div class="bg-white/80 backdrop-blur-sm p-8 rounded-3xl shadow-xl border border-gray-100">
          <h3 class="text-2xl font-bold text-gray-800 mb-8">Demande de rendez-vous</h3>
          <ContactForm @form-submitted="handleFormSubmission" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import ContactInfo from './ContactInfo.vue'
import ContactForm from './ContactForm.vue'
import GoogleMapCard from './GoogleMapCard.vue'

const handleFormSubmission = (formData) => {
  console.log('Formulaire soumis:', formData)
}
</script>