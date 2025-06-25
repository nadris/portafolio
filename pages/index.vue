<template>
  <div>
    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center justify-center overflow-hidden">
      <!-- Background gradient -->
      <div class="absolute inset-0 bg-gradient-tech opacity-20"></div>
      
      <!-- Animated background elements -->
      <div class="absolute inset-0 overflow-hidden">
        <div class="absolute -top-40 -right-40 w-96 h-96 bg-accent-400 rounded-full mix-blend-multiply filter blur-3xl opacity-40 animate-float"></div>
        <div class="absolute -bottom-40 -left-40 w-96 h-96 bg-secondary-400 rounded-full mix-blend-multiply filter blur-3xl opacity-40 animate-float" style="animation-delay: -2s;"></div>
        <div class="absolute top-40 left-40 w-96 h-96 bg-primary-400 rounded-full mix-blend-multiply filter blur-3xl opacity-40 animate-float" style="animation-delay: -4s;"></div>
        
        <!-- Grid pattern -->
        <div class="absolute inset-0 opacity-5">
          <div class="absolute inset-0" style="background-image: linear-gradient(rgba(255,255,255,0.1) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.1) 1px, transparent 1px); background-size: 50px 50px;"></div>
        </div>
      </div>

      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <div class="animate-fade-in-up space-y-8">
          <!-- Badge -->
          <div class="inline-flex items-center px-6 py-3 bg-white/10 backdrop-blur-sm rounded-full border border-white/20 text-white/90 text-sm font-medium">
            <div class="w-2 h-2 bg-accent-400 rounded-full mr-3 animate-pulse"></div>
            Arquitecto de Soluciones • Transformación Digital
          </div>
          
          <h1 class="text-5xl md:text-7xl lg:text-8xl font-heading font-black mb-8 leading-tight">
            <span class="text-text-light dark:text-text-dark block">Arquitecto de</span>
            <span class="gradient-text block animate-gradient-x">Soluciones</span>
          </h1>
          
          <p class="text-xl md:text-2xl lg:text-3xl text-text-light/80 dark:text-text-dark/80 mb-12 max-w-4xl mx-auto leading-relaxed font-light">
            Diseño <span class="font-semibold text-primary-600 dark:text-primary-400">arquitecturas escalables</span>, 
            lidero <span class="font-semibold text-secondary-600 dark:text-secondary-400">transformaciones digitales</span> 
            y construyo el <span class="font-semibold text-accent-600 dark:text-accent-400">futuro tecnológico</span> de las empresas
          </p>
          
          <div class="flex flex-col sm:flex-row gap-6 justify-center items-center">
            <NuxtLink 
              to="/proyectos"
              class="group px-10 py-5 bg-gradient-tech text-white font-bold text-lg rounded-2xl hover:shadow-tech-xl transform hover:-translate-y-2 transition-all duration-500 relative overflow-hidden"
            >
              <span class="relative z-10">Ver Proyectos</span>
              <div class="absolute inset-0 bg-gradient-tech-reverse opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
              <div class="absolute inset-0 bg-white/20 opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
            </NuxtLink>
            <NuxtLink 
              to="/sobre-mi"
              class="group px-10 py-5 border-2 border-primary-600 dark:border-primary-400 text-primary-600 dark:text-primary-400 font-bold text-lg rounded-2xl hover:bg-gradient-tech hover:text-white hover:border-transparent transform hover:-translate-y-2 transition-all duration-500 relative overflow-hidden"
            >
              <span class="relative z-10">Conoce mi Historia</span>
              <div class="absolute inset-0 bg-gradient-tech opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
            </NuxtLink>
          </div>
        </div>
      </div>

      <!-- Scroll indicator -->
      <div class="absolute bottom-12 left-1/2 transform -translate-x-1/2 animate-bounce">
        <div class="group cursor-pointer">
          <div class="w-8 h-12 border-2 border-primary-600 dark:border-primary-400 rounded-full flex justify-center relative overflow-hidden">
            <div class="w-1 h-4 bg-gradient-tech rounded-full mt-2 animate-pulse"></div>
            <div class="absolute inset-0 bg-gradient-tech opacity-0 group-hover:opacity-20 transition-opacity duration-300"></div>
          </div>
          <div class="text-center mt-2 text-primary-600 dark:text-primary-400 text-sm font-medium opacity-0 group-hover:opacity-100 transition-opacity duration-300">
            Scroll
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="py-24 bg-gradient-to-br from-gray-50 via-white to-accent-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900 relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, rgba(59, 130, 246, 0.1) 2px, transparent 2px), radial-gradient(circle at 75% 75%, rgba(147, 51, 234, 0.1) 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-20">
          <div class="inline-flex items-center px-4 py-2 bg-primary-100 dark:bg-primary-900/30 text-primary-700 dark:text-primary-300 rounded-full text-sm font-medium mb-6">
            Servicios Especializados
          </div>
          <h2 class="text-4xl md:text-5xl font-heading font-bold text-text-light dark:text-text-dark mb-6">
            Soluciones Integrales para
            <span class="gradient-text">Transformar tu Negocio</span>
          </h2>
          <p class="text-xl text-text-light/70 dark:text-text-dark/70 max-w-3xl mx-auto leading-relaxed">
            Experiencia en las tecnologías más avanzadas para crear arquitecturas que escalan con tu crecimiento
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div 
            v-for="(service, index) in services" 
            :key="index"
            class="group p-8 bg-white dark:bg-gray-800 rounded-3xl shadow-soft hover:shadow-tech-xl border border-border-light dark:border-border-dark transition-all duration-500 transform hover:-translate-y-3 relative overflow-hidden"
          >
            <!-- Background gradient on hover -->
            <div class="absolute inset-0 bg-gradient-tech opacity-0 group-hover:opacity-5 transition-opacity duration-500"></div>
            
            <!-- Floating elements -->
            <div class="absolute top-4 right-4 w-16 h-16 bg-gradient-tech rounded-full opacity-0 group-hover:opacity-10 transition-opacity duration-500 blur-xl"></div>
            
            <div class="relative z-10">
              <div class="w-20 h-20 bg-gradient-tech rounded-2xl flex items-center justify-center mb-8 group-hover:scale-110 transition-transform duration-500 shadow-tech">
                <component :is="service.icon" class="h-10 w-10 text-white" />
              </div>
              <h3 class="text-2xl font-bold text-text-light dark:text-text-dark mb-4 group-hover:text-primary-600 dark:group-hover:text-primary-400 transition-colors">
                {{ service.title }}
              </h3>
              <p class="text-text-light/70 dark:text-text-dark/70 leading-relaxed text-lg">
                {{ service.description }}
              </p>
              
              <!-- Hover effect line -->
              <div class="w-0 h-1 bg-gradient-tech mt-6 group-hover:w-full transition-all duration-500 rounded-full"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Stats Section -->
    <section class="py-24 bg-gradient-tech relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-10">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, white 2px, transparent 2px), radial-gradient(circle at 75% 75%, white 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-heading font-bold text-white mb-6">
            Resultados que <span class="text-accent-300">Hablan por Sí Mismos</span>
          </h2>
          <p class="text-xl text-white/80 max-w-3xl mx-auto">
            Métricas que demuestran el impacto real de mis soluciones en el crecimiento empresarial
          </p>
        </div>
        
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
          <div v-for="(stat, index) in stats" :key="index" class="text-center group">
            <div class="text-4xl md:text-5xl lg:text-6xl font-black text-white mb-4 group-hover:scale-110 transition-transform duration-500">
              {{ stat.value }}
            </div>
            <div class="text-white/80 text-lg font-medium">{{ stat.label }}</div>
            <div class="w-16 h-1 bg-white/30 mx-auto mt-4 group-hover:bg-white transition-colors duration-300"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-24 bg-gradient-to-br from-primary-50 via-white to-secondary-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900 relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, rgba(59, 130, 246, 0.1) 2px, transparent 2px), radial-gradient(circle at 75% 75%, rgba(147, 51, 234, 0.1) 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <div class="inline-flex items-center px-6 py-3 bg-primary-100 dark:bg-primary-900/30 text-primary-700 dark:text-primary-300 rounded-full text-sm font-medium mb-8">
          ¿Listo para el Siguiente Paso?
        </div>
        <h2 class="text-4xl md:text-5xl font-heading font-bold text-text-light dark:text-text-dark mb-8">
          ¿Listo para <span class="gradient-text">Transformar tu Negocio</span>?
        </h2>
        <p class="text-xl text-text-light/70 dark:text-text-dark/70 mb-12 max-w-3xl mx-auto leading-relaxed">
          Trabajemos juntos para crear soluciones tecnológicas que impulsen el crecimiento de tu empresa 
          y te posicionen como líder en tu industria
        </p>
        <div class="flex flex-col sm:flex-row gap-6 justify-center items-center">
          <NuxtLink 
            to="/contacto"
            class="group px-12 py-5 bg-gradient-tech text-white font-bold text-lg rounded-2xl hover:shadow-tech-xl transform hover:-translate-y-2 transition-all duration-500 relative overflow-hidden"
          >
            <span class="relative z-10">Iniciar Conversación</span>
            <div class="absolute inset-0 bg-gradient-tech-reverse opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
            <ArrowRightIcon class="ml-3 h-6 w-6 relative z-10 group-hover:translate-x-2 transition-transform duration-300" />
          </NuxtLink>
          <NuxtLink 
            to="/proyectos"
            class="group px-12 py-5 border-2 border-primary-600 dark:border-primary-400 text-primary-600 dark:text-primary-400 font-bold text-lg rounded-2xl hover:bg-gradient-tech hover:text-white hover:border-transparent transform hover:-translate-y-2 transition-all duration-500 relative overflow-hidden"
          >
            <span class="relative z-10">Ver Proyectos</span>
            <div class="absolute inset-0 bg-gradient-tech opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
          </NuxtLink>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { 
  ArrowRightIcon,
  CpuChipIcon,
  CloudIcon,
  ChartBarIcon,
  CogIcon,
  ShieldCheckIcon,
  RocketLaunchIcon
} from '@heroicons/vue/24/outline'

// SEO
useHead({
  title: 'Arquitecto de Soluciones - Liderando Transformaciones Digitales',
  meta: [
    { name: 'description', content: 'Arquitecto de Soluciones experto en diseño de arquitecturas escalables, transformación digital y liderazgo técnico. Construyo el futuro tecnológico de las empresas.' },
    { name: 'keywords', content: 'arquitecto de soluciones, transformación digital, arquitectura de software, liderazgo técnico, cloud computing' }
  ]
})

const services = [
  {
    icon: CpuChipIcon,
    title: 'Arquitectura de Software',
    description: 'Diseño de arquitecturas escalables y mantenibles que soporten el crecimiento exponencial de tu negocio con patrones modernos y mejores prácticas.'
  },
  {
    icon: CloudIcon,
    title: 'Cloud Computing',
    description: 'Migración y optimización de infraestructuras en la nube para máxima eficiencia, costos optimizados y escalabilidad automática.'
  },
  {
    icon: ChartBarIcon,
    title: 'Análisis de Datos',
    description: 'Implementación de soluciones de analytics y business intelligence para decisiones estratégicas basadas en datos en tiempo real.'
  },
  {
    icon: CogIcon,
    title: 'DevOps & CI/CD',
    description: 'Automatización completa de procesos de desarrollo y despliegue para entregas más rápidas, seguras y confiables.'
  },
  {
    icon: ShieldCheckIcon,
    title: 'Seguridad & Compliance',
    description: 'Implementación de mejores prácticas de seguridad y cumplimiento normativo para proteger tus activos digitales.'
  },
  {
    icon: RocketLaunchIcon,
    title: 'Transformación Digital',
    description: 'Liderazgo en proyectos de transformación digital y modernización de sistemas legacy para la era digital.'
  }
]

const stats = [
  { value: '50+', label: 'Proyectos Exitosos' },
  { value: '10+', label: 'Años de Experiencia' },
  { value: '100%', label: 'Clientes Satisfechos' },
  { value: '24/7', label: 'Soporte Técnico' }
]
</script>

<style scoped>
.bg-dots-pattern {
  background-image: radial-gradient(circle, #9CA3AF 1px, transparent 1px);
  background-size: 60px 60px;
}
</style> 