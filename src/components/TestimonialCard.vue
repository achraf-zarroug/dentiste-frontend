<template>
  <div class="bg-gray-50 p-8 rounded-xl hover:shadow-lg transition-shadow">
    <div class="flex items-center mb-4">
      <div v-for="star in testimonial.rating" :key="star" class="text-yellow-400 text-xl">
        ⭐
      </div>
    </div>
    <p class="text-gray-700 mb-6 italic">"{{ testimonial.content }}"</p>
    <div class="flex items-center">
      <div class="w-12 h-12 rounded-full bg-blue-100 flex items-center justify-center mr-4">
        <span class="text-blue-600 text-xl">👤</span>
      </div>
      <div>
        <p class="font-semibold text-gray-900">{{ testimonial.name }}</p>
        <p class="text-sm text-gray-600">{{ testimonial.location }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  testimonial: {
    type: Object,
    required: true
  }
})
</script>