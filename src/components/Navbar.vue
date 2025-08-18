<template>
  
  <nav class="bg-gray-900/95 backdrop-blur-sm sticky top-0 z-50 border-b border-gray-800 shadow-lg">
    <!-- BZH Badge -->
    <div class="absolute top-1 right-6 z-20">
      <div class="relative">
        <span class="text-xs text-gray-400 font-mono">בס״ד</span>
      </div>
    </div>
    <div class="container mx-auto px-4">
      <div class="flex justify-between items-center py-4">
        <!-- Logo -->
        <div class="text-2xl font-bold bg-gradient-to-r from-blue-500 to-cyan-400 bg-clip-text text-transparent">
          Nasa<span class="text-white">.Dev</span>
        </div>
        
        <!-- Desktop Menu -->
        <div class="hidden md:flex space-x-8">
          <a href="#inicio" class="text-gray-300 hover:text-white hover:bg-gray-800/50 px-4 py-2 rounded-lg transition-all duration-300 group">
            <span class="relative">Inicio
              <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-cyan-400 transition-all duration-300 group-hover:w-full"></span>
            </span>
          </a>
          <a href="#servicios" class="text-gray-300 hover:text-white hover:bg-gray-800/50 px-4 py-2 rounded-lg transition-all duration-300 group">
            <span class="relative">Servicios
              <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-cyan-400 transition-all duration-300 group-hover:w-full"></span>
            </span>
          </a>
          <a href="#testimonios" class="text-gray-300 hover:text-white hover:bg-gray-800/50 px-4 py-2 rounded-lg transition-all duration-300 group">
            <span class="relative">Testimonios
              <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-cyan-400 transition-all duration-300 group-hover:w-full"></span>
            </span>
          </a>
          <a href="#contacto" class="text-gray-300 hover:text-white hover:bg-gray-800/50 px-4 py-2 rounded-lg transition-all duration-300 group">
            <span class="relative">Contacto
              <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-cyan-400 transition-all duration-300 group-hover:w-full"></span>
            </span>
          </a>
        </div>
        
        <!-- WhatsApp Button -->
        <a 
          :href="`https://wa.me/${whatsappNumber}?text=${encodeURIComponent(whatsappMessage)}`"
          target="_blank"
          class="relative overflow-hidden bg-gradient-to-r from-blue-600 to-cyan-500 text-white px-6 py-2 rounded-lg hover:shadow-lg hover:shadow-blue-500/30 transition-all duration-300 group"
        >
          <span class="relative z-10 flex items-center">
            <span class="mr-2">💬</span> Presupuesto
          </span>
          <span class="absolute inset-0 bg-gradient-to-r from-blue-500 to-cyan-400 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></span>
        </a>
        
        <!-- Mobile Menu Button -->
        <button 
          @click="mobileMenuOpen = !mobileMenuOpen"
          class="md:hidden text-slate-700"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
      </div>
      
      <!-- Mobile Menu -->
      <div v-if="mobileMenuOpen" class="md:hidden py-4 border-t border-gray-800">
        <div class="flex flex-col space-y-4">
          <a href="#inicio" class="text-gray-300 hover:text-white hover:bg-gray-800/50 px-4 py-2 rounded-lg transition-all duration-300">Inicio</a>
          <a href="#servicios" class="text-gray-300 hover:text-white hover:bg-gray-800/50 px-4 py-2 rounded-lg transition-all duration-300">Servicios</a>
          <a href="#testimonios" class="text-gray-300 hover:text-white hover:bg-gray-800/50 px-4 py-2 rounded-lg transition-all duration-300">Testimonios</a>
          <a href="#contacto" class="text-gray-300 hover:text-white hover:bg-gray-800/50 px-4 py-2 rounded-lg transition-all duration-300">Contacto</a>
          <a 
            :href="`https://wa.me/${whatsappNumber}?text=${encodeURIComponent(whatsappMessage)}`"
            target="_blank"
            class="bg-gradient-to-r from-blue-600 to-cyan-500 text-white text-center py-2 rounded-lg hover:shadow-lg hover:shadow-blue-500/30 transition-all duration-300 mt-4"
          >
            💬 Presupuesto
          </a>
        </div>
      </div>
    </div>
     
    
  </nav>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  whatsappNumber: String,
  whatsappMessage: String
})

const mobileMenuOpen = ref(false)
</script>

<style scoped>
.text-coral-600 {
  color: #e55a4f;
}
.text-emerald-600 {
  color: #3d8b40;
}
.bg-coral-500 {
  background-color: #ff6f61;
}
.bg-coral-600 {
  background-color: #e55a4f;
}
.from-coral-500 {
  --tw-gradient-from: #ff6f61;
}
.to-coral-600 {
  --tw-gradient-to: #e55a4f;
}
.hover\:from-coral-600:hover {
  --tw-gradient-from: #e55a4f;
}
.hover\:to-coral-700:hover {
  --tw-gradient-to: #cc4a3f;
}
</style>