<template>
  <div class="bg-white p-8 rounded-xl shadow-lg">
    <form @submit.prevent="submitForm" class="space-y-6">
      <div>
        <label for="name" class="block text-sm font-medium text-gray-700 mb-2">
          Nom complet *
        </label>
        <input 
          type="text" 
          id="name" 
          v-model="form.name"
          class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-colors"
          :class="{ 'border-red-500': errors.name }"
          required
        />
        <p v-if="errors.name" class="text-red-500 text-sm mt-1">{{ errors.name }}</p>
      </div>
      
      <div>
        <label for="email" class="block text-sm font-medium text-gray-700 mb-2">
          Email *
        </label>
        <input 
          type="email" 
          id="email" 
          v-model="form.email"
          class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-colors"
          :class="{ 'border-red-500': errors.email }"
          required
        />
        <p v-if="errors.email" class="text-red-500 text-sm mt-1">{{ errors.email }}</p>
      </div>
      
      <div>
        <label for="phone" class="block text-sm font-medium text-gray-700 mb-2">
          Téléphone
        </label>
        <input 
          type="tel" 
          id="phone" 
          v-model="form.phone"
          class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-colors"
        />
      </div>
      
      <div>
        <label for="service" class="block text-sm font-medium text-gray-700 mb-2">
          Service souhaité
        </label>
        <select 
          id="service" 
          v-model="form.service"
          class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-colors"
        >
          <option value="">Sélectionnez un service</option>
          <option value="consultation">Consultation générale</option>
          <option value="nettoyage">Nettoyage dentaire</option>
          <option value="blanchiment">Blanchiment</option>
          <option value="orthodontie">Orthodontie</option>
          <option value="implant">Implants dentaires</option>
          <option value="urgence">Urgence dentaire</option>
        </select>
      </div>
      
      <div>
        <label for="message" class="block text-sm font-medium text-gray-700 mb-2">
          Message
        </label>
        <textarea 
          id="message" 
          v-model="form.message"
          rows="4"
          class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-colors"
          placeholder="Décrivez votre demande ou vos questions..."
        ></textarea>
      </div>
      
      <button 
        type="submit"
        :disabled="isSubmitting"
        class="w-full bg-blue-600 hover:bg-blue-700 disabled:bg-blue-400 text-white py-3 px-6 rounded-lg font-medium transition-colors flex items-center justify-center"
      >
        <span v-if="isSubmitting" class="mr-2">⏳</span>
        {{ isSubmitting ? 'Envoi en cours...' : 'Envoyer la demande' }}
      </button>
    </form>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'

const emit = defineEmits(['formSubmitted'])

const isSubmitting = ref(false)
const form = reactive({
  name: '',
  email: '',
  phone: '',
  service: '',
  message: ''
})

const errors = reactive({
  name: '',
  email: ''
})

const validateForm = () => {
  errors.name = ''
  errors.email = ''
  
  if (!form.name.trim()) {
    errors.name = 'Le nom est requis'
    return false
  }
  
  if (!form.email.trim()) {
    errors.email = 'L\'email est requis'
    return false
  }
  
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
  if (!emailRegex.test(form.email)) {
    errors.email = 'Format d\'email invalide'
    return false
  }
  
  return true
}

const submitForm = async () => {
  if (!validateForm()) return
  
  isSubmitting.value = true
  
  try {
    // Simulation d'un appel API
    await new Promise(resolve => setTimeout(resolve, 1000))
    
    emit('formSubmitted', { ...form })
    alert('Votre demande a été envoyée avec succès ! Nous vous contacterons bientôt.')
    
    // Reset form
    Object.keys(form).forEach(key => {
      form[key] = ''
    })
  } catch (error) {
    alert('Une erreur est survenue. Veuillez réessayer.')
  } finally {
    isSubmitting.value = false
  }
}
</script>