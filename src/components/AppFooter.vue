<template>
  <footer class="bg-gray-900 text-white py-12">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid md:grid-cols-4 gap-8">
        <div class="col-span-2">
          <div class="flex items-center mb-4">
            <div class="h-8 w-8 bg-blue-400 rounded-full flex items-center justify-center">
              <span class="text-white">😊</span>
            </div>
            <span class="ml-2 text-xl font-bold">DentalCare</span>
          </div>
          <p class="text-gray-400 mb-4">
            Votre cabinet dentaire de confiance pour des soins de qualité 
            dans un environnement moderne et accueillant.
          </p>
          <div class="flex space-x-4">
            <a href="#" class="text-gray-400 hover:text-white transition-colors text-xl" aria-label="Facebook">
              📘
            </a>
            <a href="#" class="text-gray-400 hover:text-white transition-colors text-xl" aria-label="Instagram">
              📷
            </a>
            <a href="#" class="text-gray-400 hover:text-white transition-colors text-xl" aria-label="Twitter">
              🐦
            </a>
          </div>
        </div>
        
        <div>
          <h4 class="text-lg font-semibold mb-4">Services</h4>
          <ul class="space-y-2 text-gray-400">
            <li><a href="#services" class="hover:text-white transition-colors">Consultation générale</a></li>
            <li><a href="#services" class="hover:text-white transition-colors">Nettoyage dentaire</a></li>
            <li><a href="#services" class="hover:text-white transition-colors">Blanchiment</a></li>
            <li><a href="#services" class="hover:text-white transition-colors">Orthodontie</a></li>
            <li><a href="#services" class="hover:text-white transition-colors">Implants dentaires</a></li>
          </ul>
        </div>
        
        <div>
          <h4 class="text-lg font-semibold mb-4">Contact</h4>
          <ul class="space-y-2 text-gray-400">
            <li>123 Rue de la Santé</li>
            <li>75000 Paris</li>
            <li>
              <a href="tel:0123456789" class="hover:text-white transition-colors">
                01 23 45 67 89
              </a>
            </li>
            <li>
              <a href="mailto:contact@dentalcare.fr" class="hover:text-white transition-colors">
                contact@dentalcare.fr
              </a>
            </li>
          </ul>
        </div>
      </div>
      
      <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
        <p>&copy; {{ new Date().getFullYear() }} DentalCare. Tous droits réservés.</p>
      </div>
    </div>
  </footer>
</template>