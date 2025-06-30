<script setup lang="ts">
import { RouterView } from 'vue-router'

// App.vue principal - contient seulement le router-view
</script>

<template>
  <div>
    <RouterView />
  </div>
</template>


<style>
/* Styles globaux */
html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  padding: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}

/* Custom animations */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeInUp {
  animation: fadeInUp 0.6s ease-out;
}
</style>