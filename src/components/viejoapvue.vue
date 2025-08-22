<template>
    <div class="min-h-screen min-w-screen bg-gradient-to-br from-gray-50 to-gray-100 font-sans antialiased">
      <!-- Navbar -->
      <Navbar class="min-w-screen"
        :whatsappNumber="contactData.whatsappNumber"
        :whatsappMessage="contactData.whatsappMessage"
      />
      
      <!-- Hero Section -->
      <HeroSection 
        :title="heroData.title"
        :subtitle="heroData.subtitle"
        :backgroundImage="heroData.backgroundImage"
        :whatsappNumber="contactData.whatsappNumber"
        :whatsappMessage="contactData.whatsappMessage"
      />
      
      <!-- Info Section -->
      <InfoSection 
        :title="infoData.title"
        :description="infoData.description"
        :services="infoData.services"
        :image="infoData.image"
        :whatsappNumber="contactData.whatsappNumber"
        :whatsappMessage="contactData.whatsappMessage"
      />
      
      <!-- Portfolio Section -->
      <PortfolioSection :projects="portfolioData" />
      
      <!-- Testimonials Section -->
      <TestimonialsSection :testimonials="testimonialsData" />
      
      <!-- Final CTA Section -->
      <FinalCTASection 
        :title="ctaData.title"
        :subtitle="ctaData.subtitle"
        :whatsappNumber="contactData.whatsappNumber"
        :whatsappMessage="contactData.whatsappMessage"
      />
      
      <!-- Footer -->
      <footer class="bg-gray-900 text-white py-8 relative overflow-hidden">
        <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiPjxkZWZzPjxwYXR0ZXJuIGlkPSJwYXR0ZXJuIiB3aWR0aD0iNDAiIGhlaWdodD0iNDAiIHZpZXdCb3g9IjAgMCA0MCA0MCIgcGF0dGVyblVuaXRzPSJ1c2VyU3BhY2VPblVzZSIgcGF0dGVyblRyYW5zZm9ybT0icm90YXRlKDQ1KSI+PHJlY3Qgd2lkdGg9IjIwIiBoZWlnaHQ9IjIwIiBmaWxsPSJ0cmFuc3BhcmVudCI+PC9yZWN0PjxyZWN0IHdpZHRoPSIxMCIgaGVpZ2h0PSIxMCIgZmlsbD0icmdiYSgyNTUsMjU1LDI1NSwwLjA1KSI+PC9yZWN0PjwvcGF0dGVybj48L2RlZnM+PHJlY3Qgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgZmlsbD0idXJsKCNwYXR0ZXJuKSI+PC9yZWN0Pjwvc3ZnPg==')] opacity-10"></div>
        <div class="container mx-auto px-4 text-center relative z-10">
          <p class="text-gray-300">&copy; 2025 Mijael Nasatsky - Desarrollador Web. Todos los derechos reservados.</p>
          <p class="text-gray-500 text-sm mt-2">Rosario, Argentina</p>
        </div>
      </footer>
      
      <!-- WhatsApp Floating Button -->
      <WhatsAppButton 
        :whatsappNumber="contactData.whatsappNumber"
        :whatsappMessage="contactData.whatsappMessage"
      />
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import WhatsAppButton from './components/WhatsAppButton.vue'
  import HeroSection from './components/HeroSection.vue'
  import InfoSection from './components/InfoSection.vue'
  import TestimonialsSection from './components/TestimonialsSection.vue'
  import FinalCTASection from './components/FinalCTASection.vue'
  import Navbar from './components/Navbar.vue'
  import PortfolioSection from './components/PortfolioSection.vue'
  
  // 🚀 Hero adaptado a desarrollo web
  const heroData = ref({
    title: "Desarrollo web profesional",
    subtitle: "Transformo tus ideas en sitios web modernos y funcionales",
    backgroundImage: "/placeholder.svg?height=600&width=1200"
  })
  
  // 📞 Datos de contacto
  const contactData = ref({
    whatsappNumber: "5493412114056", // Número de WhatsApp actualizado
    whatsappMessage: "Hola, quiero solicitar un presupuesto para mi proyecto web"
  })
  
  // 💻 Sección informativa sobre desarrollo web
  const infoData = ref({
    title: "Desarrollador Web Full Stack especializado en Laravel y Vue.js",
    description: "Con 4 años de experiencia en desarrollo web, me especializo en crear soluciones digitales modernas y eficientes. Desde sitios web corporativos hasta sistemas personalizados, trabajo con las últimas tecnologías para llevar tu proyecto al siguiente nivel.",
    services: [
      "Sitios web profesionales y landing pages",
      "Sistemas web personalizados con Laravel",
      "Aplicaciones SPA con Vue.js e Inertia.js",
      "E-commerce y tiendas online",
      "Optimización y mantenimiento web",
      "Integración de APIs y servicios externos"
    ],
    image: "/placeholder.svg?height=400&width=600"
  })
  
  // 🌟 Testimonios de clientes
  const testimonialsData = ref([
    {
      name: "Carlos Mendoza",
      text: "Mijael desarrolló nuestra tienda online y superó todas nuestras expectativas. Muy profesional y cumplió todos los plazos.",
      rating: 5
    },
    {
      name: "Ana Rodriguez",
      text: "El sistema de gestión que nos creó optimizó completamente nuestros procesos. Excelente trabajo y soporte post-entrega.",
      rating: 5
    },
    {
      name: "Roberto Silva",
      text: "Nuestro sitio web quedó increíble y es súper rápido. Mijael es muy detallista y sabe lo que hace.",
      rating: 5
    }
  ])
  
  // 🎯 CTA final
  const ctaData = ref({
    title: "¿Listo para llevar tu proyecto al siguiente nivel?",
    subtitle: "Solicita tu presupuesto gratuito y sin compromiso. Te respondo en menos de 24 horas."
  })
  
  // 📚 Portfolio data with the three websites
  const portfolioData = ref([
    {
      title: "Estudio Jurídico AN",
      description: "Sitio web profesional para estudio jurídico especializado en derecho laboral. Diseño elegante y funcional con formularios de contacto integrados.",
      image: "../assets/imagenes/estudioan.png", // Using the first screenshot
      url: "https://www.estudioan.com.ar/",
      technologies: ["Laravel", "Vue.js", "Tailwind CSS"],
      category: "Sitio Corporativo"
    },
    {
      title: "Mundo Fichas",
      description: "Plataforma de casino virtual líder en Latinoamérica. Sistema complejo con múltiples juegos, pagos seguros y gestión de usuarios.",
      image: "https://blobs.vusercontent.net/blob/hero-data-zYgOI5N9z5vkM2hFTa6F9ZOcetViZb.tsx", // Using the second screenshot  
      url: "https://www.mundofichas.com/",
      technologies: ["Laravel", "Vue.js", "API Integration"],
      category: "Plataforma Web"
    },
    {
      title: "Marcela Cocina",
      description: "Sitio web gastronómico con menú digital interactivo. Diseño responsive optimizado para dispositivos móviles con sistema de pedidos.",
      image: "https://blobs.vusercontent.net/blob/hero-data-zYgOI5N9z5vkM2hFTa6F9ZOcetViZb.tsx", // Using the third screenshot
      url: "https://marcela-cocina.vercel.app/",
      technologies: ["Vuejs.js", "Laravel", "Vercel", "Responsive Design"],
      category: "E-commerce"
    }
  ])
  </script>
  
  <style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
  
  /* Prevent horizontal scrolling */
  html, body {
    max-width: 100%;
    overflow-x: hidden;
  }
  
  /* Ensure all elements stay within viewport */
  * {
    box-sizing: border-box;
  }
  
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
  }
  </style>