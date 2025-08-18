<template>
  <section id="inicio" class="relative min-h-screen flex items-center justify-center overflow-hidden bg-gradient-to-br from-gray-900 to-gray-800">
   
    <!-- Grid Pattern Overlay -->
    <div class="absolute inset-0 z-0 opacity-10" style="background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiPjxkZWZzPjxwYXR0ZXJuIGlkPSJwYXR0ZXJuIiB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHZpZXdCb3g9IjAgMCA2MCA2MCIgcGF0dGVyblVuaXRzPSJ1c2VyU3BhY2VPblVzZSIgcGF0dGVyblRyYW5zZm9ybT0icm90YXRlKDQ1KSI+PHBhdGggZD0iTTM0LjE0IDI1Ljg2TDM0LjE0IDEyLjE3TDI1Ljg2IDIwLjQ4TDE0LjExIDguNzNMMi4zNCAyMC41TDIwLjQ4IDM4LjY0TDM0LjE0IDI1Ljg2WiIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJyZ2JhKDI1NSwyNTUsMjU1LDAuMDUpIiBzdHJva2Utd2lkdGg9IjEiLz48L3BhdHRlcm4+PC9kZWZzPjxyZWN0IHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIGZpbGw9InVybCgjcGF0dGVybikiLz48L3N2Zz4=');"></div>
    
    <!-- Animated Background Elements -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="absolute top-1/4 left-1/4 w-64 h-64 bg-blue-500/10 rounded-full filter blur-3xl animate-pulse"></div>
      <div class="absolute bottom-1/3 right-1/4 w-96 h-96 bg-cyan-500/10 rounded-full filter blur-3xl animate-pulse animation-delay-2000"></div>
      <div class="absolute top-1/3 right-1/3 w-48 h-48 bg-purple-500/10 rounded-full filter blur-3xl animate-pulse animation-delay-4000"></div>
    </div>
    
    <!-- Content -->
    <div class="relative z-10 container mx-auto px-4 text-center">
      <div class="max-w-4xl mx-auto">
        <!-- Badge -->
        <div class="inline-flex items-center px-4 py-2 bg-white/10 backdrop-blur-sm rounded-full text-sm font-medium text-cyan-300 mb-8 border border-cyan-400/20 shadow-lg shadow-cyan-500/10">
          <span class="w-2 h-2 bg-cyan-400 rounded-full mr-2 animate-pulse"></span>
          <span class="text-cyan-200">Disponible para nuevos proyectos</span>
        </div>
        
        <!-- Main Title -->
        <h1 class="text-5xl md:text-7xl font-bold text-white mb-6 leading-tight">
          {{ title }}
          <span class="block text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-blue-500">
            que convierte
          </span>
        </h1>
        
        <!-- Subtitle -->
        <p class="text-xl md:text-2xl text-gray-300 mb-10 max-w-2xl mx-auto leading-relaxed">
          {{ subtitle }}
        </p>
        
        <!-- Tech Stack -->
        <div class="flex flex-wrap justify-center gap-3 mb-12">
          <span v-for="(tech, index) in techStack" :key="tech" 
                class="px-4 py-2 bg-white/5 backdrop-blur-sm rounded-lg text-sm font-medium text-gray-200 border border-gray-700/50 shadow-lg hover:bg-white/10 hover:border-cyan-400/30 hover:text-white transition-all duration-300"
                :class="{
                  'hover:shadow-cyan-500/20': index % 3 === 0,
                  'hover:shadow-blue-500/20': index % 3 === 1,
                  'hover:shadow-purple-500/20': index % 3 === 2
                }">
            {{ tech }}
          </span>
        </div>
        
        <!-- CTA Buttons -->
        <div class="flex flex-col sm:flex-row gap-6 justify-center">
          <a 
            :href="`https://wa.me/${whatsappNumber}?text=${encodeURIComponent(whatsappMessage)}`"
            target="_blank"
            class="group relative overflow-hidden bg-gradient-to-r from-blue-600 to-cyan-500 text-white px-8 py-4 rounded-lg text-lg font-semibold transition-all duration-300 shadow-lg hover:shadow-xl hover:shadow-blue-500/30 transform hover:-translate-y-0.5"
          >
            <span class="relative z-10 flex items-center justify-center">
              <span class="mr-2">🚀</span> Solicitar Presupuesto
            </span>
            <span class="absolute inset-0 bg-gradient-to-r from-blue-500 to-cyan-400 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></span>
          </a>
          <a 
            href="#servicios"
            class="bg-white/90 backdrop-blur-sm text-slate-700 px-8 py-4 rounded-full text-lg font-semibold hover:bg-white transition-all duration-300 shadow-lg hover:shadow-xl transform hover:-translate-y-1"
          >
            Ver Servicios
          </a>
        </div>
      </div>
    </div>
    
    <!-- Scroll Indicator -->
    <div
      @click="scrollToNextSection"
      class="absolute bottom-8 cursor-pointer left-1/2 transform -translate-x-1/2 animate-bounce focus:outline-none"
      aria-label="Desplazarse hacia abajo"
    > 
      <svg class="w-6 h-6 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
      </svg>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  title: String,
  subtitle: String,
  backgroundImage: String,
  whatsappNumber: String,
  whatsappMessage: String
})

const scrollToNextSection = () => {
  const nextSection = document.querySelector('#servicios')
  if (nextSection) {
    nextSection.scrollIntoView({ behavior: 'smooth' })
  }
}
const techStack = ref([
  'Laravel', 'Vue.js', 'Inertia.js', 'Tailwind CSS', 'MySQL', 'PHP'
])
</script>