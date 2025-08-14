<template>
  <section id="contacto" class="py-20 bg-gradient-to-r from-slate-500 to-emerald-500 relative overflow-hidden">
    <!-- Background Pattern -->
    <div class="absolute inset-0 opacity-10">
      <div class="absolute inset-0" style="background-image: url('data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.4'%3E%3Ccircle cx='30' cy='30' r='2'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E')"></div>
    </div>
    
    <div class="container mx-auto px-4 text-center relative z-10">
      <div class="max-w-4xl mx-auto">
        <!-- Main CTA -->
        <h2 class="text-4xl md:text-6xl font-bold text-white mb-6 leading-tight">
          {{ title }}
        </h2>
        <p class="text-xl md:text-2xl text-white/90 mb-10 max-w-2xl mx-auto leading-relaxed">
          {{ subtitle }}
        </p>
        
        <!-- Contact Options -->
        <div class="grid md:grid-cols-2 gap-6 mb-12 max-w-2xl mx-auto">
          <!-- WhatsApp -->
          <a 
            :href="`https://wa.me/${whatsappNumber}?text=${encodeURIComponent(whatsappMessage)}`"
            target="_blank"
            class="bg-white text-slate-800 p-6 rounded-2xl shadow-xl hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-2 group"
          >
            <div class="flex items-center justify-center mb-3 group-hover:scale-110 transition-transform">
              <svg 
    xmlns="http://www.w3.org/2000/svg" 
    width="40" height="40" 
    viewBox="0 0 24 24" 
    fill="currentColor" 
    class="w-10 h-10 text-green-500"
>
  <path d="M20.52 3.48A11.78 11.78 0 0 0 12 0C5.37 0 0 5.37 0 12c0 2.12.55 4.18 1.59 6.03L0 24l6.15-1.6A11.93 11.93 0 0 0 12 24c6.63 0 12-5.37 12-12 0-3.2-1.25-6.21-3.48-8.52zM12 22c-1.87 0-3.69-.5-5.28-1.44l-.38-.23-3.65.95.97-3.56-.25-.37A9.92 9.92 0 0 1 2 12C2 6.49 6.49 2 12 2c2.67 0 5.18 1.04 7.07 2.93A9.94 9.94 0 0 1 22 12c0 5.51-4.49 10-10 10zm5.26-7.34c-.29-.14-1.71-.84-1.97-.94s-.46-.14-.65.14c-.2.29-.75.93-.92 1.12-.17.2-.34.23-.63.08-.9-.45-1.73-1-2.43-1.73a9.86 9.86 0 0 1-1.64-2.02c-.17-.29-.02-.45.13-.6.14-.14.29-.37.43-.55.14-.18.17-.32.26-.54.09-.21.04-.4-.02-.55-.06-.14-.65-1.55-.89-2.12-.23-.56-.47-.49-.65-.5-.17 0-.37 0-.56 0-.2 0-.52.07-.8.37-.27.29-1.04 1.02-1.04 2.48s1.06 2.87 1.21 3.07c.15.2 2.09 3.18 5.08 4.46.71.31 1.26.5 1.69.64.71.23 1.35.2 1.86.12.57-.09 1.73-.71 1.98-1.39.25-.68.25-1.26.18-1.38-.07-.11-.26-.18-.55-.32z"/>
</svg>

            </div>
            <h3 class="text-xl font-bold mb-2 flex items-center justify-center">
              
              WhatsApp
            </h3>
            <p class="text-slate-600 text-center">Respuesta inmediata</p>
          </a>
          
          <!-- Email -->
          <a 
            href="mailto:mijael.nasa@hotmail.com"
            class="bg-white text-slate-800 p-6 rounded-2xl shadow-xl hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-2 group"
          >
            <div class="text-4xl mb-3 group-hover:scale-110 transition-transform">📧</div>
            <h3 class="text-xl font-bold mb-2">Email</h3>
            <p class="text-slate-600">mija191100@gmail.com</p>
          </a>
        </div>
        
        <!-- Main CTA Button -->
        <a 
          :href="`https://wa.me/${whatsappNumber}?text=${encodeURIComponent(whatsappMessage)}`"
          target="_blank"
          class="inline-flex items-center bg-white text-slate-800 px-10 py-5 rounded-full text-xl font-bold hover:bg-slate-50 transition-all duration-300 shadow-2xl hover:shadow-3xl transform hover:-translate-y-1"
        >
          🚀 Empezar mi proyecto ahora
          <svg class="w-6 h-6 ml-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path>
          </svg>
        </a>
        
        <!-- Additional Info -->
        <div class="mt-12 grid grid-cols-1 md:grid-cols-3 gap-6 text-white/80">
          <div>
            <div class="text-2xl font-bold text-white mb-1">Gratis</div>
            <div class="text-sm">Consulta inicial</div>
          </div>
          <div>
            <div class="text-2xl font-bold text-white mb-1">24hs</div>
            <div class="text-sm">Tiempo de respuesta</div>
          </div>
          <div>
            <div class="text-2xl font-bold text-white mb-1">100%</div>
            <div class="text-sm">Sin compromiso</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  title: String,
  subtitle: String,
  whatsappNumber: String,
  whatsappMessage: String
})
</script>