<template>
  <div class="group bg-white/70 backdrop-blur-sm p-8 rounded-3xl shadow-lg hover:shadow-2xl transition-all duration-500 border border-gray-100 hover:border-gray-200 transform hover:-translate-y-2">
    <div class="relative mb-6">
      <div :class="`w-16 h-16 bg-gradient-to-br ${service.color} rounded-2xl flex items-center justify-center shadow-lg group-hover:shadow-xl transition-all duration-300 group-hover:scale-110`">
        <span class="text-2xl">{{ service.icon }}</span>
      </div>
      <div class="absolute -top-1 -right-1 w-4 h-4 bg-yellow-400 rounded-full opacity-0 group-hover:opacity-100 transition-all duration-300 animate-pulse"></div>
    </div>
    
    <h3 class="text-xl font-bold text-gray-800 mb-4 group-hover:text-teal-600 transition-colors">
      {{ service.title }}
    </h3>
    
    <p class="text-gray-600 mb-6 leading-relaxed">
      {{ service.description }}
    </p>
    
    <div class="flex items-center justify-between">
      <div class="text-teal-600 font-bold text-lg">
        {{ service.price }}
      </div>
      <button 
        @click="$emit('learnMore', service.id)"
        class="group/btn text-teal-600 hover:text-teal-700 font-medium flex items-center transition-all duration-300"
      >
      
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps({
  service: {
    type: Object,
    required: true
  }
})

defineEmits(['learnMore'])
</script>