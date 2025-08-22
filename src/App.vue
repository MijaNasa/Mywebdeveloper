<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100 p-4">
    <div class="max-w-4xl mx-auto">
      <!-- Header -->
      <div class="text-center mb-8">
        <h1 class="text-4xl font-bold text-indigo-900 mb-2">🏆 Cacería del Tesoro</h1>
        <p class="text-lg text-indigo-700">Completa todos los desafíos y gana!</p>
      </div>

      <!-- Participant Name -->
      <div class="bg-white rounded-lg shadow-md p-6 mb-6">
        <label class="block text-sm font-medium text-gray-700 mb-2">
          Nombre del participante:
        </label>
        <input
          v-model="participantName"
          type="text"
          placeholder="Ingresa tu nombre completo"
          class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500"
        />
      </div>

      <!-- Progress Bar -->
      <div class="bg-white rounded-lg shadow-md p-6 mb-6">
        <div class="flex justify-between items-center mb-2">
          <span class="text-sm font-medium text-gray-700">Progreso</span>
          <span class="text-sm text-gray-500">{{ completedChallenges }}/{{ totalChallenges }}</span>
        </div>
        <div class="w-full bg-gray-200 rounded-full h-3">
          <div 
            class="bg-gradient-to-r from-green-400 to-green-600 h-3 rounded-full transition-all duration-300"
            :style="{ width: progressPercentage + '%' }"
          ></div>
        </div>
      </div>

      <!-- Challenge Categories -->
      <div class="space-y-6">
        <!-- Conversación -->
        <div class="bg-white rounded-lg shadow-md overflow-hidden">
          <div class="bg-gradient-to-r from-purple-500 to-purple-600 px-6 py-4">
            <h2 class="text-xl font-bold text-white flex items-center">
              💬 Desafíos de conversación
            </h2>
          </div>
          <div class="p-6 space-y-4">
            <div v-for="(challenge, index) in conversationChallenges" :key="index" class="challenge-item">
              <div class="flex items-start space-x-3">
                <input
                  v-model="challenge.completed"
                  type="checkbox"
                  class="mt-1 h-5 w-5 text-purple-600 focus:ring-purple-500 border-gray-300 rounded"
                />
                <div class="flex-1">
                  <p class="text-gray-800 font-medium mb-2">{{ challenge.text }}</p>
                  <textarea
                    v-model="challenge.response"
                    placeholder="Escribe tu respuesta aquí..."
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-purple-500 focus:border-purple-500 text-sm"
                    rows="2"
                  ></textarea>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Fotos/Selfies -->
        <div class="bg-white rounded-lg shadow-md overflow-hidden">
          <div class="bg-gradient-to-r from-pink-500 to-pink-600 px-6 py-4">
            <h2 class="text-xl font-bold text-white flex items-center">
              📸 Desafíos con fotos / selfies
            </h2>
          </div>
          <div class="p-6 space-y-4">
            <div v-for="(challenge, index) in photoChallenges" :key="index" class="challenge-item">
              <div class="flex items-start space-x-3">
                <input
                  v-model="challenge.completed"
                  type="checkbox"
                  class="mt-1 h-5 w-5 text-pink-600 focus:ring-pink-500 border-gray-300 rounded"
                />
                <div class="flex-1">
                  <p class="text-gray-800 font-medium mb-2">{{ challenge.text }}</p>
                  <textarea
                    v-model="challenge.response"
                    placeholder="Una vez tengas la foto, guardala y marca como completado el desafio. Al final, envia todas las fotos"
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-pink-500 focus:border-pink-500 text-sm"
                    rows="2"
                  ></textarea>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Divertidos/Acción -->
        <div class="bg-white rounded-lg shadow-md overflow-hidden">
          <div class="bg-gradient-to-r from-orange-500 to-orange-600 px-6 py-4">
            <h2 class="text-xl font-bold text-white flex items-center">
              🎲 Desafíos divertidos / de acción
            </h2>
          </div>
          <div class="p-6 space-y-4">
            <div v-for="(challenge, index) in actionChallenges" :key="index" class="challenge-item">
              <div class="flex items-start space-x-3">
                <input
                  v-model="challenge.completed"
                  type="checkbox"
                  class="mt-1 h-5 w-5 text-orange-600 focus:ring-orange-500 border-gray-300 rounded"
                />
                <div class="flex-1">
                  <p class="text-gray-800 font-medium mb-2">{{ challenge.text }}</p>
                  <textarea
                    v-model="challenge.response"
                    placeholder="Cuenta cómo fue la experiencia..."
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-orange-500 focus:border-orange-500 text-sm"
                    rows="2"
                  ></textarea>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Búsqueda -->
        <div class="bg-white rounded-lg shadow-md overflow-hidden">
          <div class="bg-gradient-to-r from-green-500 to-green-600 px-6 py-4">
            <h2 class="text-xl font-bold text-white flex items-center">
              🕵 Desafíos de búsqueda
            </h2>
          </div>
          <div class="p-6 space-y-4">
            <div v-for="(challenge, index) in searchChallenges" :key="index" class="challenge-item">
              <div class="flex items-start space-x-3">
                <input
                  v-model="challenge.completed"
                  type="checkbox"
                  class="mt-1 h-5 w-5 text-green-600 focus:ring-green-500 border-gray-300 rounded"
                />
                <div class="flex-1">
                  <p class="text-gray-800 font-medium mb-2">{{ challenge.text }}</p>
                  <textarea
                    v-model="challenge.response"
                    placeholder="Escribe lo que descubriste..."
                    class="w-full px-3 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-green-500 focus:border-green-500 text-sm"
                    rows="2"
                  ></textarea>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Submit Button -->
      <div v-if="allChallengesCompleted" class="mt-8 text-center">
        <button
          @click="sendToWhatsApp"
          class="bg-gradient-to-r from-green-500 to-green-600 hover:from-green-600 hover:to-green-700 text-white font-bold py-4 px-8 rounded-lg text-lg shadow-lg transform hover:scale-105 transition-all duration-200"
        >
          🎉 ¡Enviar por WhatsApp! 🎉
        </button>
        <p class="text-sm text-gray-600 mt-2">¡Felicitaciones! Has completado todos los desafíos</p>
      </div>

      <!-- Footer -->
      <div class="text-center mt-12 text-gray-500 text-sm">
        <p>¡Diviértete y conoce gente nueva! 🌟</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const participantName = ref('')

const conversationChallenges = ref([
  {
    text: 'Encuentra a alguien que no sea de tu ciudad y pregúntale qué lo trajo al evento.',
    completed: false,
    response: ''
  },
  {
    text: 'Habla con alguien sobre su comida judía favorita y anótala en tu lista.',
    completed: false,
    response: ''
  },
  {
    text: 'Descubre quién fue a Israel y pregúntale qué lugar le gustó más.',
    completed: false,
    response: ''
  },
  {
    text: 'Averigua el segundo nombre de tres personas diferentes.',
    completed: false,
    response: ''
  },
  {
    text: 'Encuentra a alguien que haya participado en un campamento o viaje judío y pregúntale cómo fue su experiencia.',
    completed: false,
    response: ''
  }
])

const photoChallenges = ref([
  {
    text: 'Sacate una selfie con dos personas que no conocías antes del evento.',
    completed: false,
    response: ''
  },
  {
    text: 'Sacate una foto grupal con al menos 5 personas de distintas ciudades.',
    completed: false,
    response: ''
  },
  {
    text: 'Hacé una foto divertida imitando una escena de Shabat o Jag.',
    completed: false,
    response: ''
  },
  {
    text: 'Selfie con alguien que tenga tu misma inicial en el nombre.',
    completed: false,
    response: ''
  },
  {
    text: 'Selfie con alguien que tenga un accesorio llamativo (gorra, pulsera, collar, etc.).',
    completed: false,
    response: ''
  }
])

const actionChallenges = ref([
  {
    text: 'Jugá una partida rápida de cartas o un mini-juego con alguien nuevo.',
    completed: false,
    response: ''
  },
  {
    text: 'Contale un chiste a alguien y anotá si se rió.',
    completed: false,
    response: ''
  },
  {
    text: 'Enseñale una palabra en otro idioma a alguien y aprendé una de ellos.',
    completed: false,
    response: ''
  },
  {
    text: 'Intercambiá un objeto pequeño (ej. pulsera, lapicera, gorrita) con alguien.',
    completed: false,
    response: ''
  },
  {
    text: 'Encontrá a alguien que sepa bailar rikudim y pedile que te enseñe un paso.',
    completed: false,
    response: ''
  }
])

const searchChallenges = ref([
  {
    text: 'Encontrá a alguien que haya nacido el mismo mes que vos.',
    completed: false,
    response: ''
  },
  {
    text: 'Encontrá a alguien que tenga el mismo hobby que vos.',
    completed: false,
    response: ''
  },
  {
    text: 'Encontrá a alguien que sepa tocar un instrumento y pedile que te lo muestre (o te lo cuente).',
    completed: false,
    response: ''
  },
  {
    text: 'Descubrí quién tiene más hermanos/as en el grupo.',
    completed: false,
    response: ''
  },
  {
    text: 'Encontrá a alguien que haya leído el mismo libro o visto la misma serie que vos.',
    completed: false,
    response: ''
  }
])

const allChallenges = computed(() => [
  ...conversationChallenges.value,
  ...photoChallenges.value,
  ...actionChallenges.value,
  ...searchChallenges.value
])

const totalChallenges = computed(() => allChallenges.value.length)

const completedChallenges = computed(() => 
  allChallenges.value.filter(challenge => challenge.completed).length
)

const progressPercentage = computed(() => 
  totalChallenges.value > 0 ? (completedChallenges.value / totalChallenges.value) * 100 : 0
)

const allChallengesCompleted = computed(() => 
  completedChallenges.value === totalChallenges.value && participantName.value.trim() !== ''
)

const sendToWhatsApp = () => {
  if (!participantName.value.trim()) {
    alert('Por favor ingresa tu nombre antes de enviar')
    return
  }

  let message = `🏆 CACERÍA DEL TESORO COMPLETADA 🏆\n\n`
  message += `Participante: ${participantName.value}\n\n`

  message += `💬 DESAFÍOS DE CONVERSACIÓN:\n`
  conversationChallenges.value.forEach((challenge, index) => {
    message += `${index + 1}. ${challenge.text}\n`
    message += `Respuesta: ${challenge.response || 'Sin respuesta'}\n\n`
  })

  message += `📸 DESAFÍOS CON FOTOS/SELFIES:\n`
  photoChallenges.value.forEach((challenge, index) => {
    message += `${index + 1}. ${challenge.text}\n`
    message += `Respuesta: ${challenge.response || 'Sin respuesta'}\n\n`
  })

  message += `🎲 DESAFÍOS DIVERTIDOS/DE ACCIÓN:\n`
  actionChallenges.value.forEach((challenge, index) => {
    message += `${index + 1}. ${challenge.text}\n`
    message += `Respuesta: ${challenge.response || 'Sin respuesta'}\n\n`
  })

  message += `🕵 DESAFÍOS DE BÚSQUEDA:\n`
  searchChallenges.value.forEach((challenge, index) => {
    message += `${index + 1}. ${challenge.text}\n`
    message += `Respuesta: ${challenge.response || 'Sin respuesta'}\n\n`
  })

  const phoneNumber = '5493412114056'
  const encodedMessage = encodeURIComponent(message)
  const whatsappUrl = `https://wa.me/${phoneNumber}?text=${encodedMessage}`
  
  window.open(whatsappUrl, '_blank')
}
</script>

<style scoped>
.challenge-item {
  border-bottom: 1px solid #e5e7eb;
  padding-bottom: 1rem;
  margin-bottom: 1rem;
}


</style>