<template>
  <div class="min-h-screen bg-background-light dark:bg-background-dark">
    <!-- Hero Section -->
    <section class="pt-20 pb-16 bg-gradient-tech relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-10">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, white 2px, transparent 2px), radial-gradient(circle at 75% 75%, white 2px, transparent 2px); background-size: 50px 50px;"></div>
      </div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <h1 class="text-4xl md:text-5xl font-heading font-bold text-white mb-6">
          Contacto
        </h1>
        <p class="text-xl text-white/90 max-w-3xl mx-auto">
          ¿Tienes un proyecto en mente? Hablemos sobre cómo puedo ayudarte 
          a transformar tu visión en una solución tecnológica escalable
        </p>
      </div>
    </section>

    <!-- Contact Form & Info -->
    <section class="py-24 bg-gradient-to-br from-gray-50 via-white to-accent-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900 relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, rgba(59, 130, 246, 0.1) 2px, transparent 2px), radial-gradient(circle at 75% 75%, rgba(147, 51, 234, 0.1) 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-2 gap-16">
          <!-- Contact Form -->
          <div class="space-y-8">
            <div>
              <div class="inline-flex items-center px-4 py-2 bg-primary-100 dark:bg-primary-900/30 text-primary-700 dark:text-primary-300 rounded-full text-sm font-medium mb-6">
                Iniciar Conversación
              </div>
              <h2 class="text-3xl md:text-4xl font-heading font-bold text-text-light dark:text-text-dark mb-4">
                Cuéntame sobre tu <span class="gradient-text">Proyecto</span>
              </h2>
              <p class="text-lg text-text-light/70 dark:text-text-dark/70 leading-relaxed">
                Completa el formulario y me pondré en contacto contigo en menos de 24 horas para discutir cómo puedo ayudarte.
              </p>
            </div>

            <form @submit.prevent="submitForm" class="space-y-6">
              <div class="grid md:grid-cols-2 gap-6">
                <div>
                  <label for="firstName" class="block text-sm font-semibold text-text-light dark:text-text-dark mb-2">
                    Nombre *
                  </label>
                  <input
                    id="firstName"
                    v-model="form.firstName"
                    type="text"
                    required
                    class="w-full px-6 py-4 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-300"
                    placeholder="Tu nombre"
                  />
                </div>
                <div>
                  <label for="lastName" class="block text-sm font-semibold text-text-light dark:text-text-dark mb-2">
                    Apellido *
                  </label>
                  <input
                    id="lastName"
                    v-model="form.lastName"
                    type="text"
                    required
                    class="w-full px-6 py-4 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-300"
                    placeholder="Tu apellido"
                  />
                </div>
              </div>

              <div>
                <label for="email" class="block text-sm font-semibold text-text-light dark:text-text-dark mb-2">
                  Email *
                </label>
                <input
                  id="email"
                  v-model="form.email"
                  type="email"
                  required
                  class="w-full px-6 py-4 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-300"
                  placeholder="tu@email.com"
                />
              </div>

              <div>
                <label for="company" class="block text-sm font-semibold text-text-light dark:text-text-dark mb-2">
                  Empresa
                </label>
                <input
                  id="company"
                  v-model="form.company"
                  type="text"
                  class="w-full px-6 py-4 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-300"
                  placeholder="Nombre de tu empresa"
                />
              </div>

              <div>
                <label for="projectType" class="block text-sm font-semibold text-text-light dark:text-text-dark mb-2">
                  Tipo de Proyecto *
                </label>
                <select
                  id="projectType"
                  v-model="form.projectType"
                  required
                  class="w-full px-6 py-4 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-300"
                >
                  <option value="">Selecciona el tipo de proyecto</option>
                  <option value="architecture">Arquitectura de Software</option>
                  <option value="cloud">Migración Cloud</option>
                  <option value="transformation">Transformación Digital</option>
                  <option value="devops">DevOps & CI/CD</option>
                  <option value="consulting">Consultoría Técnica</option>
                  <option value="other">Otro</option>
                </select>
              </div>

              <div>
                <label for="budget" class="block text-sm font-semibold text-text-light dark:text-text-dark mb-2">
                  Presupuesto Estimado
                </label>
                <select
                  id="budget"
                  v-model="form.budget"
                  class="w-full px-6 py-4 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-300"
                >
                  <option value="">Selecciona un rango</option>
                  <option value="small">$10K - $50K</option>
                  <option value="medium">$50K - $200K</option>
                  <option value="large">$200K - $1M</option>
                  <option value="enterprise">$1M+</option>
                  <option value="discuss">Prefiero discutirlo</option>
                </select>
              </div>

              <div>
                <label for="message" class="block text-sm font-semibold text-text-light dark:text-text-dark mb-2">
                  Descripción del Proyecto *
                </label>
                <textarea
                  id="message"
                  v-model="form.message"
                  required
                  rows="6"
                  class="w-full px-6 py-4 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-all duration-300 resize-none"
                  placeholder="Cuéntame sobre tu proyecto, objetivos, desafíos y cualquier información relevante..."
                ></textarea>
              </div>

              <button
                type="submit"
                :disabled="isSubmitting"
                class="group w-full px-8 py-4 bg-gradient-tech text-white font-bold text-lg rounded-2xl hover:shadow-tech-xl transform hover:-translate-y-1 transition-all duration-500 relative overflow-hidden disabled:opacity-50 disabled:cursor-not-allowed"
              >
                <span class="relative z-10">
                  {{ isSubmitting ? 'Enviando...' : 'Enviar Mensaje' }}
                </span>
                <div class="absolute inset-0 bg-gradient-tech-reverse opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                <ArrowRightIcon v-if="!isSubmitting" class="ml-3 h-6 w-6 relative z-10 group-hover:translate-x-2 transition-transform duration-300" />
              </button>
            </form>
          </div>

          <!-- Contact Info -->
          <div class="space-y-8">
            <div>
              <div class="inline-flex items-center px-4 py-2 bg-accent-100 dark:bg-accent-900/30 text-accent-700 dark:text-accent-300 rounded-full text-sm font-medium mb-6">
                Información de Contacto
              </div>
              <h2 class="text-3xl md:text-4xl font-heading font-bold text-text-light dark:text-text-dark mb-4">
                Conectemos y <span class="gradient-text">Construyamos Juntos</span>
              </h2>
              <p class="text-lg text-text-light/70 dark:text-text-dark/70 leading-relaxed">
                Estoy disponible para discutir tu proyecto y explorar cómo podemos trabajar juntos para alcanzar tus objetivos tecnológicos.
              </p>
            </div>

            <!-- Contact Methods -->
            <div class="space-y-6">
              <div class="group p-6 bg-white dark:bg-gray-800 rounded-2xl shadow-soft border border-border-light dark:border-border-dark hover:shadow-tech transition-all duration-300 transform hover:-translate-y-1">
                <div class="flex items-center space-x-4">
                  <div class="w-12 h-12 bg-gradient-tech rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300 shadow-tech">
                    <EnvelopeIcon class="h-6 w-6 text-white" />
                  </div>
                  <div>
                    <h3 class="text-lg font-semibold text-text-light dark:text-text-dark">Email</h3>
                    <p class="text-primary-600 dark:text-primary-400">contacto@arquitectosoluciones.com</p>
                    <p class="text-sm text-text-light/60 dark:text-text-dark/60">Respuesta en menos de 24 horas</p>
                  </div>
                </div>
              </div>

              <div class="group p-6 bg-white dark:bg-gray-800 rounded-2xl shadow-soft border border-border-light dark:border-border-dark hover:shadow-tech transition-all duration-300 transform hover:-translate-y-1">
                <div class="flex items-center space-x-4">
                  <div class="w-12 h-12 bg-gradient-tech rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300 shadow-tech">
                    <PhoneIcon class="h-6 w-6 text-white" />
                  </div>
                  <div>
                    <h3 class="text-lg font-semibold text-text-light dark:text-text-dark">Teléfono</h3>
                    <p class="text-primary-600 dark:text-primary-400">+1 (555) 123-4567</p>
                    <p class="text-sm text-text-light/60 dark:text-text-dark/60">Lun - Vie, 9:00 AM - 6:00 PM</p>
                  </div>
                </div>
              </div>

              <div class="group p-6 bg-white dark:bg-gray-800 rounded-2xl shadow-soft border border-border-light dark:border-border-dark hover:shadow-tech transition-all duration-300 transform hover:-translate-y-1">
                <div class="flex items-center space-x-4">
                  <div class="w-12 h-12 bg-gradient-tech rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300 shadow-tech">
                    <MapPinIcon class="h-6 w-6 text-white" />
                  </div>
                  <div>
                    <h3 class="text-lg font-semibold text-text-light dark:text-text-dark">Ubicación</h3>
                    <p class="text-primary-600 dark:text-primary-400">Remoto / Híbrido</p>
                    <p class="text-sm text-text-light/60 dark:text-text-dark/60">Disponible para proyectos globales</p>
                  </div>
                </div>
              </div>
            </div>

            <!-- Social Links -->
            <div class="space-y-4">
              <h3 class="text-xl font-semibold text-text-light dark:text-text-dark">Sígueme en Redes Sociales</h3>
              <div class="flex space-x-4">
                <a
                  href="https://linkedin.com"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="group p-4 bg-gradient-tech rounded-xl hover:shadow-tech transform hover:-translate-y-1 transition-all duration-300"
                >
                  <svg class="h-6 w-6 text-white group-hover:scale-110 transition-transform duration-300" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                  </svg>
                </a>
                <a
                  href="https://github.com"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="group p-4 bg-gradient-tech rounded-xl hover:shadow-tech transform hover:-translate-y-1 transition-all duration-300"
                >
                  <svg class="h-6 w-6 text-white group-hover:scale-110 transition-transform duration-300" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                  </svg>
                </a>
                <a
                  href="https://twitter.com"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="group p-4 bg-gradient-tech rounded-xl hover:shadow-tech transform hover:-translate-y-1 transition-all duration-300"
                >
                  <svg class="h-6 w-6 text-white group-hover:scale-110 transition-transform duration-300" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/>
                  </svg>
                </a>
              </div>
            </div>

            <!-- Response Time -->
            <div class="p-6 bg-gradient-tech rounded-2xl text-white">
              <h3 class="text-xl font-bold mb-3">Tiempo de Respuesta</h3>
              <div class="space-y-2">
                <div class="flex items-center space-x-3">
                  <div class="w-2 h-2 bg-white rounded-full"></div>
                  <span>Email: < 24 horas</span>
                </div>
                <div class="flex items-center space-x-3">
                  <div class="w-2 h-2 bg-white rounded-full"></div>
                  <span>Llamada: < 2 horas (horario laboral)</span>
                </div>
                <div class="flex items-center space-x-3">
                  <div class="w-2 h-2 bg-white rounded-full"></div>
                  <span>Consulta inicial: Gratuita</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-24 bg-gradient-tech relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-10">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, white 2px, transparent 2px), radial-gradient(circle at 75% 75%, white 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-heading font-bold text-white mb-6">
            Preguntas <span class="text-accent-300">Frecuentes</span>
          </h2>
          <p class="text-xl text-white/80 max-w-3xl mx-auto">
            Respuestas a las preguntas más comunes sobre mis servicios y proceso de trabajo
          </p>
        </div>

        <div class="space-y-6">
          <div
            v-for="(faq, index) in faqs"
            :key="index"
            class="bg-white/10 backdrop-blur-sm rounded-2xl p-6 border border-white/20"
          >
            <h3 class="text-xl font-semibold text-white mb-3">{{ faq.question }}</h3>
            <p class="text-white/80 leading-relaxed">{{ faq.answer }}</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import {
  ArrowRightIcon,
  EnvelopeIcon,
  PhoneIcon,
  MapPinIcon
} from '@heroicons/vue/24/outline'

// SEO
useHead({
  title: 'Contacto - Arquitecto de Soluciones',
  meta: [
    { name: 'description', content: 'Contacta conmigo para discutir tu proyecto de arquitectura de software, transformación digital o consultoría técnica. Respuesta en menos de 24 horas.' }
  ]
})

const form = ref({
  firstName: '',
  lastName: '',
  email: '',
  company: '',
  projectType: '',
  budget: '',
  message: ''
})

const isSubmitting = ref(false)

const submitForm = async () => {
  isSubmitting.value = true
  
  // Simular envío del formulario
  await new Promise(resolve => setTimeout(resolve, 2000))
  
  // Aquí iría la lógica real de envío del formulario
  console.log('Formulario enviado:', form.value)
  
  // Reset form
  form.value = {
    firstName: '',
    lastName: '',
    email: '',
    company: '',
    projectType: '',
    budget: '',
    message: ''
  }
  
  isSubmitting.value = false
  
  // Mostrar mensaje de éxito (aquí podrías usar un toast o modal)
  alert('¡Gracias por tu mensaje! Te responderé en menos de 24 horas.')
}

const faqs = [
  {
    question: '¿Cuál es tu proceso de trabajo?',
    answer: 'Mi proceso incluye: 1) Consulta inicial gratuita para entender tus necesidades, 2) Análisis y propuesta detallada, 3) Diseño de arquitectura, 4) Implementación y desarrollo, 5) Despliegue y seguimiento continuo.'
  },
  {
    question: '¿Trabajas con empresas de cualquier tamaño?',
    answer: 'Sí, trabajo con startups, empresas medianas y grandes corporaciones. Cada proyecto se adapta a las necesidades específicas y presupuesto del cliente.'
  },
  {
    question: '¿Ofreces servicios de mantenimiento y soporte?',
    answer: 'Absolutamente. Ofrezco planes de mantenimiento continuo, monitoreo 24/7, actualizaciones de seguridad y soporte técnico para asegurar que tu solución funcione de manera óptima.'
  },
  {
    question: '¿Cuánto tiempo toma completar un proyecto típico?',
    answer: 'El tiempo varía según la complejidad. Proyectos pequeños pueden tomar 2-4 semanas, mientras que transformaciones digitales completas pueden tomar 3-6 meses. Siempre proporciono cronogramas detallados.'
  },
  {
    question: '¿Trabajas de forma remota o presencial?',
    answer: 'Trabajo principalmente de forma remota, lo que me permite servir clientes globales de manera eficiente. Para proyectos que lo requieran, puedo hacer visitas presenciales ocasionales.'
  }
]
</script> 