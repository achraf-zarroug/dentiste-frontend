<template>
  <div class="flex items-start">
    <div class="bg-blue-100 p-2 rounded-full mr-4 mt-1">
      <span class="text-blue-600">✓</span>
    </div>
    <div>
      <h4 class="font-semibold text-gray-900">{{ feature.title }}</h4>
      <p class="text-gray-600">{{ feature.description }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  feature: {
    type: Object,
    required: true
  }
})
</script>