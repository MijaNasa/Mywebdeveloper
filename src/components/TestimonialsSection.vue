<template>
  <section id="testimonios" class="relative py-20 bg-gradient-to-br from-gray-900 to-gray-800 overflow-hidden">
    <!-- Grid Pattern Overlay -->
    <div class="absolute inset-0 z-0 opacity-10" style="background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiPjxkZWZzPjxwYXR0ZXJuIGlkPSJwYXR0ZXJuIiB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHZpZXdCb3g9IjAgMCA2MCA2MCIgcGF0dGVyblVuaXRzPSJ1c2VyU3BhY2VPblVzZSIgcGF0dGVyblRyYW5zZm9ybT0icm90YXRlKDQ1KSI+PHBhdGggZD0iTTM0LjE0IDI1Ljg2TDM0LjE0IDEyLjE3TDI1Ljg2IDIwLjQ4TDE0LjExIDguNzNMMi4zNCAyMC41TDIwLjQ4IDM4LjY0TDM0LjE0IDI1Ljg2WiIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJyZ2JhKDI1NSwyNTUsMjU1LDAuMDUpIiBzdHJva2Utd2lkdGg9IjEiLz48L3BhdHRlcm4+PC9kZWZzPjxyZWN0IHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIGZpbGw9InVybCgjcGF0dGVybikiLz48L3N2Zz4=');"></div>
    
    <!-- Animated Background Elements -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="absolute top-1/4 left-1/4 w-64 h-64 bg-blue-500/10 rounded-full filter blur-3xl animate-pulse"></div>
      <div class="absolute bottom-1/3 right-1/4 w-96 h-96 bg-cyan-500/10 rounded-full filter blur-3xl animate-pulse animation-delay-2000"></div>
      <div class="absolute top-1/3 right-1/3 w-48 h-48 bg-purple-500/10 rounded-full filter blur-3xl animate-pulse animation-delay-4000"></div>
    </div>
    <div class="container mx-auto px-4">
      <!-- Section Header -->
      <div class="text-center mb-16 relative z-10">
        <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">
          Lo que dicen mis <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-emerald-400">clientes</span>
        </h2>
        <p class="text-xl text-gray-300 max-w-2xl mx-auto">
          La satisfacción de mis clientes es mi mayor motivación
        </p>
      </div>
      
      <!-- Testimonials Grid -->
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="testimonial in testimonials" :key="testimonial.name"
             class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-2 border border-gray-700">
          <!-- Stars -->
          <div class="flex mb-4">
            <svg v-for="star in testimonial.rating" :key="star"
                 class="w-5 h-5 text-yellow-400 fill-current" viewBox="0 0 20 20">
              <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"/>
            </svg>
          </div>
          
          <!-- Testimonial Text -->
          <p class="text-slate-600 h-24 mb-6 leading-relaxed">
            "{{ testimonial.text }}"
          </p>
          
          <!-- Author -->
          <div class="flex items-center">
            <div class="w-12 h-12 bg-gradient-to-r from-slate-500 to-emerald-500 rounded-full flex items-center justify-center text-white font-bold text-lg mr-4">
              {{ testimonial.name.charAt(0) }}
            </div>
            <div>
              <div class="font-semibold text-slate-800">{{ testimonial.name }}</div>
              <div class="text-sm text-slate-500">Cliente verificado</div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Trust Indicators -->
      <div class="mt-16 text-center">
        <div class="inline-flex items-center space-x-8 bg-white/80 backdrop-blur-sm px-8 py-4 rounded-full shadow-lg">
          <div class="flex items-center space-x-2">
            <div class="w-3 h-3 bg-emerald-500 rounded-full"></div>
            <span class="text-slate-700 font-medium">Respuesta en 24hs</span>
          </div>
          <div class="flex items-center space-x-2">
            <div class="w-3 h-3 bg-yellow-500 rounded-full"></div>
            <span class="text-slate-700 font-medium">Garantía de calidad</span>
          </div>
          <div class="flex items-center space-x-2">
            <div class="w-3 h-3 bg-blue-500 rounded-full"></div>
            <span class="text-slate-700 font-medium">Soporte post-entrega</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  testimonials: Array
})
</script>