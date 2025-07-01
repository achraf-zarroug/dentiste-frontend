<template>
  <section id="services" class="py-20 relative">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <div class="inline-flex items-center px-4 py-2 bg-teal-50 rounded-full text-teal-600 text-sm font-medium mb-4">
          <span class="mr-2">✨</span>
          Nos Services
        </div>
        <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-6">
          Votre dentiste à Zarzis, spécialiste des soins dentaires d’excellence
        </h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Une gamme complète de traitements dentaires avec les dernières technologies 
          pour votre confort et votre bien-être.
        </p>
      </div>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <ServiceCard 
          v-for="service in services" 
          :key="service.id"
          :service="service"
          @learn-more="handleLearnMore"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import ServiceCard from './ServiceCard.vue'

const services = ref([
  {
    id: 1,
    title: 'Consultation & Diagnostic',
    description: 'Examen complet avec imagerie numérique et plan de traitement personnalisé.',
    icon: '🔍',
    color: 'from-blue-400 to-blue-500',
    price: 'À partir de 80 DT'
  },
  {
    id: 2,
    title: 'Soins Conservateurs',
    description: 'Traitement des caries, obturations esthétiques et soins de la pulpe.',
    icon: '🦷',
    color: 'from-teal-400 to-teal-500',
    price: 'À partir de 120 DT'
  },
  {
    id: 3,
    title: 'Parodontologie',
    description: 'Traitement des maladies des gencives et maintien de la santé parodontale.',
    icon: '🌿',
    color: 'from-green-400 to-green-500',
    price: 'À partir de 150 DT'
  },
  {
    id: 4,
    title: 'Orthodontie',
    description: 'Correction de l\'alignement dentaire avec appareils modernes et invisibles.',
    icon: '✨',
    color: 'from-purple-400 to-purple-500',
    price: 'Sur devis'
  },
  {
    id: 5,
    title: 'Implantologie',
    description: 'Remplacement des dents manquantes par des implants de haute qualité.',
    icon: '⚡',
    color: 'from-orange-400 to-orange-500',
    price: 'À partir de 1200 DT'
  },
  {
    id: 6,
    title: 'Esthétique Dentaire',
    description: 'Blanchiment, facettes et sourire design pour un résultat parfait.',
    icon: '💎',
    color: 'from-pink-400 to-pink-500',
    price: 'À partir de 300 DT'
  }
])

const handleLearnMore = (serviceId) => {
  console.log('En savoir plus sur le service:', serviceId)
}
</script>