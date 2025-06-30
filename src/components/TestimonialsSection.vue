<template>
  <section class="py-20 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">
          Ce que disent nos patients
        </h2>
        <p class="text-xl text-gray-600">
          La satisfaction de nos patients est notre plus belle récompense
        </p>
      </div>
      
      <div class="grid md:grid-cols-3 gap-8">
        <TestimonialCard 
          v-for="testimonial in testimonials" 
          :key="testimonial.id"
          :testimonial="testimonial"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import TestimonialCard from './TestimonialCard.vue'

const testimonials = ref([
  {
    id: 1,
    name: 'Marie Dubois',
    location: 'Paris',
    content: 'Excellent service ! L\'équipe est très professionnelle et l\'accueil chaleureux. Je recommande vivement ce cabinet.',
    rating: 5
  },
  {
    id: 2,
    name: 'Pierre Martin',
    location: 'Boulogne',
    content: 'Des soins de qualité dans un environnement moderne. Le Dr. Dupont a su me mettre en confiance dès la première visite.',
    rating: 5
  },
  {
    id: 3,
    name: 'Sophie Laurent',
    location: 'Neuilly',
    content: 'Très satisfaite de mon traitement d\'orthodontie. Résultats parfaits et suivi impeccable tout au long du processus.',
    rating: 5
  }
])
</script>