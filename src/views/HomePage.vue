<template>
  <div class="home-page">
    <AppHeader />
    <HeroSection />
    <ServicesSection />
    <AboutSection />
    <TestimonialsSection />
    <ContactSection />
    <AppFooter />
  </div>
</template>

<script setup>
import AppHeader from '../components/AppHeader.vue'
import HeroSection from '../components/HeroSection.vue'
import ServicesSection from '../components/ServicesSection.vue'
import AboutSection from '../components/AboutSection.vue'
import TestimonialsSection from '../components/TestimonialsSection.vue'
import ContactSection from '../components/ContactSection.vue'
import AppFooter from '../components/AppFooter.vue'
</script>