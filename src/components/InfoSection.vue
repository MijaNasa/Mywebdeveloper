<template>
  <section id="servicios" class="py-20 bg-white">
    <div class="container mx-auto px-4">
      <div class="grid lg:grid-cols-2 gap-12 items-center">
        <!-- Content -->
        <div class="order-2 lg:order-1">
          <h2 class="text-4xl md:text-5xl font-bold text-slate-800 mb-6">
            {{ title }}
          </h2>
          <p class="text-lg text-slate-600 mb-8 leading-relaxed">
            {{ description }}
          </p>
          
          <!-- Services List -->
          <div class="space-y-4 mb-8">
            <div v-for="service in services" :key="service" 
                 class="flex items-start space-x-3">
              <div class="flex-shrink-0 w-6 h-6 bg-gradient-to-r from-coral-500 to-emerald-500 rounded-full flex items-center justify-center mt-0.5">
                <svg class="w-3 h-3 text-white" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                </svg>
              </div>
              <span class="text-slate-700 font-medium">{{ service }}</span>
            </div>
          </div>
          
          <!-- Stats -->
          <div class="grid grid-cols-3 gap-6 mb-8">
            <div class="text-center">
              <div class="text-3xl font-bold text-coral-600 mb-1">4+</div>
              <div class="text-sm text-slate-600">Años experiencia</div>
            </div>
            <div class="text-center">
              <div class="text-3xl font-bold text-emerald-600 mb-1">50+</div>
              <div class="text-sm text-slate-600">Proyectos completados</div>
            </div>
            <div class="text-center">
              <div class="text-3xl font-bold text-blue-600 mb-1">100%</div>
              <div class="text-sm text-slate-600">Clientes satisfechos</div>
            </div>
          </div>
          
          <!-- CTA Button -->
          <a 
            :href="`https://wa.me/${whatsappNumber}?text=${encodeURIComponent(whatsappMessage)}`"
            target="_blank"
            class="inline-flex items-center bg-gradient-to-r from-coral-500 to-coral-600 text-black px-8 py-4 rounded-full text-lg font-semibold hover:from-coral-600 hover:to-coral-700 transition-all duration-300 shadow-lg hover:shadow-xl transform hover:-translate-y-0.5"
          >
            💬 Hablemos de tu proyecto
            <svg class="w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path>
            </svg>
          </a>
        </div>
        
        <!-- Image -->
        <div class="order-1 lg:order-2">
          <div class="relative">
            <img 
              src="../assets/imagenes/desarrollo.jpg" 
              alt="Desarrollador web trabajando"
              class="w-full h-96 object-cover rounded-2xl shadow-2xl"
            />
            <div class="absolute inset-0 bg-gradient-to-tr from-coral-500/20 to-emerald-500/20 rounded-2xl"></div>
            
            <!-- Floating Elements -->
            <div class="absolute -top-4 -right-4 bg-white p-4 rounded-xl shadow-lg">
              <div class="text-2xl">💻</div>
            </div>
            <div class="absolute -bottom-4 -left-4 bg-white p-4 rounded-xl shadow-lg">
              <div class="text-2xl">🚀</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
  services: Array,
  image: String,
  whatsappNumber: String,
  whatsappMessage: String
})
</script>