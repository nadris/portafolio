<template>
  <div class="min-h-screen bg-background-light dark:bg-background-dark transition-colors duration-500">
    <!-- Header/Navigation -->
    <header class="sticky top-0 z-50 bg-white/95 dark:bg-background-dark/95 backdrop-blur-xl border-b border-border-light/50 dark:border-border-dark/50 shadow-soft">
      <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-20">
          <!-- Logo -->
          <div class="flex items-center">
            <NuxtLink to="/" class="group relative">
              <div class="text-3xl font-heading font-black gradient-text hover:scale-110 transition-all duration-500 relative z-10">
                AS
              </div>
              <div class="absolute inset-0 bg-gradient-tech rounded-xl opacity-0 group-hover:opacity-20 blur-xl transition-opacity duration-500"></div>
            </NuxtLink>
          </div>

          <!-- Desktop Navigation -->
          <div class="hidden md:flex items-center space-x-1">
            <NuxtLink 
              v-for="item in navigationItems" 
              :key="item.path"
              :to="item.path"
              class="relative px-6 py-3 text-text-light dark:text-text-dark hover:text-primary-600 dark:hover:text-primary-400 transition-all duration-300 font-medium rounded-xl group overflow-hidden"
              active-class="text-primary-600 dark:text-primary-400 bg-primary-50 dark:bg-primary-900/20"
            >
              <span class="relative z-10">{{ item.name }}</span>
              <div class="absolute inset-0 bg-gradient-tech opacity-0 group-hover:opacity-10 transition-opacity duration-300 rounded-xl"></div>
              <div class="absolute bottom-0 left-0 w-0 h-0.5 bg-gradient-tech transition-all duration-500 group-hover:w-full rounded-full"></div>
            </NuxtLink>
          </div>

          <!-- Right side - Dark mode toggle and mobile menu -->
          <div class="flex items-center space-x-3">
            <!-- Dark mode toggle -->
            <button
              @click="toggleColorMode"
              class="group p-3 rounded-xl bg-gradient-tech text-white hover:shadow-tech-xl transform hover:-translate-y-1 transition-all duration-300 relative overflow-hidden"
              :aria-label="colorMode.value === 'dark' ? 'Switch to light mode' : 'Switch to dark mode'"
            >
              <div class="absolute inset-0 bg-gradient-tech-reverse opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
              <SunIcon v-if="colorMode.value === 'dark'" class="h-5 w-5 relative z-10" />
              <MoonIcon v-else class="h-5 w-5 relative z-10" />
            </button>

            <!-- Mobile menu button -->
            <button
              @click="mobileMenuOpen = !mobileMenuOpen"
              class="md:hidden group p-3 rounded-xl bg-gradient-tech text-white hover:shadow-tech-xl transform hover:-translate-y-1 transition-all duration-300 relative overflow-hidden"
              aria-label="Toggle mobile menu"
            >
              <div class="absolute inset-0 bg-gradient-tech-reverse opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
              <Bars3Icon v-if="!mobileMenuOpen" class="h-5 w-5 relative z-10" />
              <XMarkIcon v-else class="h-5 w-5 relative z-10" />
            </button>
          </div>
        </div>

        <!-- Mobile Navigation -->
        <Transition
          enter-active-class="transition ease-out duration-300"
          enter-from-class="opacity-0 -translate-y-2"
          enter-to-class="opacity-100 translate-y-0"
          leave-active-class="transition ease-in duration-200"
          leave-from-class="opacity-100 translate-y-0"
          leave-to-class="opacity-0 -translate-y-2"
        >
          <div v-if="mobileMenuOpen" class="md:hidden py-6 border-t border-border-light/50 dark:border-border-dark/50 bg-white/95 dark:bg-background-dark/95 backdrop-blur-xl">
            <div class="flex flex-col space-y-2">
              <NuxtLink
                v-for="item in navigationItems"
                :key="item.path"
                :to="item.path"
                @click="mobileMenuOpen = false"
                class="group px-4 py-3 text-text-light dark:text-text-dark hover:text-primary-600 dark:hover:text-primary-400 transition-all duration-300 font-medium rounded-xl hover:bg-gradient-tech hover:text-white relative overflow-hidden"
                active-class="text-primary-600 dark:text-primary-400 bg-primary-50 dark:bg-primary-900/20"
              >
                <span class="relative z-10">{{ item.name }}</span>
                <div class="absolute inset-0 bg-gradient-tech opacity-0 group-hover:opacity-100 transition-opacity duration-300 rounded-xl"></div>
              </NuxtLink>
            </div>
          </div>
        </Transition>
      </nav>
    </header>

    <!-- Main Content -->
    <main>
      <slot />
    </main>

    <!-- Footer -->
    <footer class="relative bg-gradient-tech text-white overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-10">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, white 2px, transparent 2px), radial-gradient(circle at 75% 75%, white 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div class="grid md:grid-cols-3 gap-12 mb-12">
          <!-- Company Info -->
          <div class="space-y-6">
            <div>
              <h3 class="text-3xl font-heading font-bold mb-4">Arquitecto de Soluciones</h3>
              <p class="text-white/90 text-lg leading-relaxed">
                Transformando ideas en arquitecturas escalables y soluciones tecnológicas innovadoras que impulsan el crecimiento empresarial.
              </p>
            </div>
            <div class="flex space-x-4">
              <a
                href="https://linkedin.com"
                target="_blank"
                rel="noopener noreferrer"
                class="group p-3 bg-white/10 rounded-xl hover:bg-white/20 transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg"
              >
                <span class="sr-only">LinkedIn</span>
                <svg class="h-6 w-6 group-hover:scale-110 transition-transform duration-300" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                </svg>
              </a>
              <a
                href="https://github.com"
                target="_blank"
                rel="noopener noreferrer"
                class="group p-3 bg-white/10 rounded-xl hover:bg-white/20 transition-all duration-300 transform hover:-translate-y-1 hover:shadow-lg"
              >
                <span class="sr-only">GitHub</span>
                <svg class="h-6 w-6 group-hover:scale-110 transition-transform duration-300" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
              </a>
            </div>
          </div>

          <!-- Quick Links -->
          <div class="space-y-6">
            <h4 class="text-xl font-semibold mb-6">Enlaces Rápidos</h4>
            <ul class="space-y-4">
              <li v-for="item in navigationItems.slice(1, 5)" :key="item.path">
                <NuxtLink 
                  :to="item.path" 
                  class="group text-white/80 hover:text-white transition-all duration-300 flex items-center space-x-2"
                >
                  <div class="w-1 h-1 bg-white/60 group-hover:bg-white rounded-full transition-all duration-300"></div>
                  <span class="group-hover:translate-x-1 transition-transform duration-300">{{ item.name }}</span>
                </NuxtLink>
              </li>
            </ul>
          </div>

          <!-- Contact Info -->
          <div class="space-y-6">
            <h4 class="text-xl font-semibold mb-6">¿Listo para Transformar tu Negocio?</h4>
            <div class="space-y-4 text-white/90">
              <p class="text-lg">Tengo un proyecto en mente que necesita una arquitectura escalable y moderna.</p>
              <p>Hablemos sobre cómo puedo ayudarte a transformar tu visión en realidad tecnológica.</p>
              <NuxtLink 
                to="/contacto"
                class="group inline-flex items-center px-8 py-4 bg-white text-primary-600 font-semibold rounded-xl hover:bg-gray-50 transform hover:-translate-y-1 transition-all duration-300 shadow-lg hover:shadow-xl"
              >
                <span>Iniciar Conversación</span>
                <ArrowRightIcon class="ml-3 h-5 w-5 group-hover:translate-x-1 transition-transform duration-300" />
              </NuxtLink>
            </div>
          </div>
        </div>

        <div class="border-t border-white/20 pt-8 text-center">
          <p class="text-white/70">
            © {{ new Date().getFullYear() }} Arquitecto de Soluciones. Construyendo el futuro tecnológico.
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { SunIcon, MoonIcon, Bars3Icon, XMarkIcon, ArrowRightIcon } from '@heroicons/vue/24/outline'

const colorMode = useColorMode()
const mobileMenuOpen = ref(false)

const navigationItems = [
  { name: 'Inicio', path: '/' },
  { name: 'Sobre mí', path: '/sobre-mi' },
  { name: 'Proyectos', path: '/proyectos' },
  { name: 'Habilidades', path: '/habilidades' },
  { name: 'Certificaciones', path: '/certificaciones' },
  { name: 'Experiencia', path: '/experiencia' },
  { name: 'Contacto', path: '/contacto' }
]

const toggleColorMode = () => {
  colorMode.preference = colorMode.value === 'dark' ? 'light' : 'dark'
}
</script> 