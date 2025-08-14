<template>
  <a
    :href="`https://wa.me/${whatsappNumber}?text=${encodeURIComponent(whatsappMessage)}`"
    target="_blank"
    rel="noopener noreferrer"
    aria-label="Chatear por WhatsApp"
    class="fixed bottom-8 right-8 z-50 w-16 h-16 bg-green-500 hover:bg-green-600 rounded-full flex items-center justify-center shadow-lg transition-transform transform hover:scale-110 hover:shadow-xl"
  >
    <!-- Ícono oficial de WhatsApp -->
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 24 24"
      class="w-10 h-10 text-white"
      fill="currentColor"
      aria-hidden="true"
    >
      <path d="M20.52 3.48A11.78 11.78 0 0 0 12 0C5.37 0 0 5.37 0 12c0 2.12.55 4.18 1.59 6.03L0 24l6.15-1.6A11.93 11.93 0 0 0 12 24c6.63 0 12-5.37 12-12 0-3.2-1.25-6.21-3.48-8.52zM12 22c-1.87 0-3.69-.5-5.28-1.44l-.38-.23-3.65.95.97-3.56-.25-.37A9.92 9.92 0 0 1 2 12C2 6.49 6.49 2 12 2c2.67 0 5.18 1.04 7.07 2.93A9.94 9.94 0 0 1 22 12c0 5.51-4.49 10-10 10zm5.26-7.34c-.29-.14-1.71-.84-1.97-.94s-.46-.14-.65.14c-.2.29-.75.93-.92 1.12-.17.2-.34.23-.63.08-.9-.45-1.73-1-2.43-1.73a9.86 9.86 0 0 1-1.64-2.02c-.17-.29-.02-.45.13-.6.14-.14.29-.37.43-.55.14-.18.17-.32.26-.54.09-.21.04-.4-.02-.55-.06-.14-.65-1.55-.89-2.12-.23-.56-.47-.49-.65-.5-.17 0-.37 0-.56 0-.2 0-.52.07-.8.37-.27.29-1.04 1.02-1.04 2.48s1.06 2.87 1.21 3.07c.15.2 2.09 3.18 5.08 4.46.71.31 1.26.5 1.69.64.71.23 1.35.2 1.86.12.57-.09 1.73-.71 1.98-1.39.25-.68.25-1.26.18-1.38-.07-.11-.26-.18-.55-.32z"/>
    </svg>


  </a>
</template>

<script setup>
defineProps({
  whatsappNumber: {
    type: String,
    default: "5493412114056"
  },
  whatsappMessage: {
    type: String,
    default: "Hola, quiero consultar sobre tu servicio"
  }
})
</script>
