<template>
  <section id="about" class="py-20 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="lg:grid lg:grid-cols-2 lg:gap-12 items-center">
        <div class="mb-12 lg:mb-0">
          <div class="bg-gradient-to-br from-gray-100 to-gray-50 rounded-2xl shadow-lg w-full h-80 flex items-center justify-center">
            <div class="text-center">
              <div class="text-6xl mb-4">👥</div>
              <p class="text-blue-600 font-medium">Équipe dentaire professionnelle</p>
            </div>
          </div>
        </div>
        <div>
          <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-6">
            Une équipe dédiée à votre bien-être
          </h2>
          <p class="text-lg text-gray-600 mb-6">
            Avec plus de 15 ans d'expérience, notre cabinet dentaire s'engage à vous offrir 
            des soins de qualité dans un environnement moderne et accueillant.
          </p>
          <div class="space-y-4">
            <FeatureItem 
              v-for="feature in features" 
              :key="feature.id"
              :feature="feature"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import FeatureItem from './FeatureItem.vue'

const features = ref([
  {
    id: 1,
    title: 'Équipements modernes',
    description: 'Technologies de pointe pour des soins précis et confortables'
  },
  {
    id: 2,
    title: 'Équipe expérimentée',
    description: 'Dentistes qualifiés et personnel attentionné'
  },
  {
    id: 3,
    title: 'Approche personnalisée',
    description: 'Soins adaptés aux besoins de chaque patient'
  }
])
</script>