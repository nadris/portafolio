<template>
  <div>
    <!-- Hero Section -->
    <section class="py-20 bg-gradient-to-br from-primary-50 via-white to-accent-50 dark:from-secondary-900 dark:via-secondary-800 dark:to-secondary-900">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h1 class="text-4xl md:text-5xl font-heading font-bold text-secondary-900 dark:text-white mb-6">
            Sobre <span class="gradient-text">Mí</span>
          </h1>
          <p class="text-xl text-secondary-600 dark:text-secondary-400 max-w-3xl mx-auto">
            Arquitecto de Soluciones con más de una década de experiencia diseñando y liderando transformaciones digitales
          </p>
        </div>
        
        <div class="grid lg:grid-cols-2 gap-12 items-center">
          <!-- Profile Image -->
          <div class="relative">
            <div class="relative mx-auto w-80 h-80 lg:w-96 lg:h-96">
              <div class="absolute inset-0 bg-gradient-to-br from-primary-400 to-accent-400 rounded-full blur-3xl opacity-20"></div>
              <div class="relative w-full h-full bg-gradient-to-br from-primary-500 to-accent-500 rounded-full flex items-center justify-center shadow-2xl">
                <div class="text-white text-6xl font-bold">AS</div>
              </div>
            </div>
          </div>
          
          <!-- Professional Summary -->
          <div class="space-y-6">
            <h2 class="text-2xl font-heading font-bold text-secondary-900 dark:text-white">
              Visión Estratégica
            </h2>
            <p class="text-lg text-secondary-700 dark:text-secondary-300 leading-relaxed">
              Mi enfoque se centra en crear arquitecturas que no solo resuelvan los desafíos técnicos actuales, 
              sino que también anticipen las necesidades futuras del negocio. Creo firmemente en que la tecnología 
              debe ser un habilitador estratégico, no solo un costo operativo.
            </p>
            <p class="text-lg text-secondary-700 dark:text-secondary-300 leading-relaxed">
              Con experiencia en empresas Fortune 500 y startups, he desarrollado la capacidad de adaptar 
              soluciones a diferentes contextos empresariales, siempre manteniendo los más altos estándares 
              de calidad y escalabilidad.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Core Values -->
    <section class="py-16 bg-white dark:bg-secondary-800">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12">
          <h2 class="text-3xl font-heading font-bold text-secondary-900 dark:text-white mb-4">
            Valores Fundamentales
          </h2>
          <p class="text-lg text-secondary-600 dark:text-secondary-400">
            Los principios que guían mi trabajo y liderazgo
          </p>
        </div>
        
        <div class="grid md:grid-cols-3 gap-8">
          <div class="text-center p-6">
            <div class="w-16 h-16 bg-primary-100 dark:bg-primary-900 rounded-full flex items-center justify-center mx-auto mb-4">
              <LightBulbIcon class="h-8 w-8 text-primary-600 dark:text-primary-400" />
            </div>
            <h3 class="text-xl font-semibold text-secondary-900 dark:text-white mb-3">
              Innovación Estratégica
            </h3>
            <p class="text-secondary-600 dark:text-secondary-400">
              Busco constantemente nuevas formas de resolver problemas complejos, 
              combinando tecnologías emergentes con metodologías probadas.
            </p>
          </div>
          
          <div class="text-center p-6">
            <div class="w-16 h-16 bg-accent-100 dark:bg-accent-900 rounded-full flex items-center justify-center mx-auto mb-4">
              <UserGroupIcon class="h-8 w-8 text-accent-600 dark:text-accent-400" />
            </div>
            <h3 class="text-xl font-semibold text-secondary-900 dark:text-white mb-3">
              Liderazgo Colaborativo
            </h3>
            <p class="text-secondary-600 dark:text-secondary-400">
              Creo en el poder del trabajo en equipo y en desarrollar el talento 
              de los demás para lograr resultados excepcionales.
            </p>
          </div>
          
          <div class="text-center p-6">
            <div class="w-16 h-16 bg-secondary-100 dark:bg-secondary-700 rounded-full flex items-center justify-center mx-auto mb-4">
              <ShieldCheckIcon class="h-8 w-8 text-secondary-600 dark:text-secondary-400" />
            </div>
            <h3 class="text-xl font-semibold text-secondary-900 dark:text-white mb-3">
              Excelencia Técnica
            </h3>
            <p class="text-secondary-600 dark:text-secondary-400">
              Mantengo los más altos estándares de calidad, seguridad y rendimiento 
              en todas las soluciones que diseño e implemento.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Professional Journey -->
    <section class="py-16 bg-secondary-50 dark:bg-secondary-900">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12">
          <h2 class="text-3xl font-heading font-bold text-secondary-900 dark:text-white mb-4">
            Mi Trayectoria Profesional
          </h2>
          <p class="text-lg text-secondary-600 dark:text-secondary-400">
            Una evolución constante en el mundo de la tecnología
          </p>
        </div>
        
        <div class="space-y-8">
          <div class="bg-white dark:bg-secondary-800 p-8 rounded-xl shadow-soft">
            <div class="flex flex-col md:flex-row gap-6">
              <div class="md:w-1/3">
                <h3 class="text-xl font-semibold text-secondary-900 dark:text-white mb-2">
                  Arquitecto de Soluciones Senior
                </h3>
                <p class="text-primary-600 dark:text-primary-400 font-medium">2020 - Presente</p>
              </div>
              <div class="md:w-2/3">
                <p class="text-secondary-700 dark:text-secondary-300 mb-4">
                  Liderando el diseño e implementación de arquitecturas cloud-native para empresas Fortune 500. 
                  Especializado en microservicios, contenedores y automatización de infraestructura.
                </p>
                <ul class="space-y-2 text-secondary-600 dark:text-secondary-400">
                  <li class="flex items-center">
                    <CheckCircleIcon class="h-5 w-5 text-accent-500 mr-2 flex-shrink-0" />
                    Diseño de arquitecturas escalables para aplicaciones de alto tráfico
                  </li>
                  <li class="flex items-center">
                    <CheckCircleIcon class="h-5 w-5 text-accent-500 mr-2 flex-shrink-0" />
                    Implementación de estrategias de DevOps y CI/CD
                  </li>
                  <li class="flex items-center">
                    <CheckCircleIcon class="h-5 w-5 text-accent-500 mr-2 flex-shrink-0" />
                    Mentoría técnica y liderazgo de equipos de desarrollo
                  </li>
                </ul>
              </div>
            </div>
          </div>
          
          <div class="bg-white dark:bg-secondary-800 p-8 rounded-xl shadow-soft">
            <div class="flex flex-col md:flex-row gap-6">
              <div class="md:w-1/3">
                <h3 class="text-xl font-semibold text-secondary-900 dark:text-white mb-2">
                  Ingeniero de Software Senior
                </h3>
                <p class="text-primary-600 dark:text-primary-400 font-medium">2017 - 2020</p>
              </div>
              <div class="md:w-2/3">
                <p class="text-secondary-700 dark:text-secondary-300 mb-4">
                  Desarrollo de aplicaciones empresariales y migración de sistemas legacy a la nube. 
                  Experiencia en múltiples tecnologías y frameworks.
                </p>
                <ul class="space-y-2 text-secondary-600 dark:text-secondary-400">
                  <li class="flex items-center">
                    <CheckCircleIcon class="h-5 w-5 text-accent-500 mr-2 flex-shrink-0" />
                    Migración exitosa de sistemas monolíticos a arquitecturas distribuidas
                  </li>
                  <li class="flex items-center">
                    <CheckCircleIcon class="h-5 w-5 text-accent-500 mr-2 flex-shrink-0" />
                    Optimización de rendimiento y escalabilidad de aplicaciones
                  </li>
                  <li class="flex items-center">
                    <CheckCircleIcon class="h-5 w-5 text-accent-500 mr-2 flex-shrink-0" />
                    Implementación de prácticas de desarrollo ágil
                  </li>
                </ul>
              </div>
            </div>
          </div>
          
          <div class="bg-white dark:bg-secondary-800 p-8 rounded-xl shadow-soft">
            <div class="flex flex-col md:flex-row gap-6">
              <div class="md:w-1/3">
                <h3 class="text-xl font-semibold text-secondary-900 dark:text-white mb-2">
                  Desarrollador Full Stack
                </h3>
                <p class="text-primary-600 dark:text-primary-400 font-medium">2015 - 2017</p>
              </div>
              <div class="md:w-2/3">
                <p class="text-secondary-700 dark:text-secondary-300 mb-4">
                  Desarrollo de aplicaciones web y móviles. Adquisición de experiencia 
                  en múltiples tecnologías frontend y backend.
                </p>
                <ul class="space-y-2 text-secondary-600 dark:text-secondary-400">
                  <li class="flex items-center">
                    <CheckCircleIcon class="h-5 w-5 text-accent-500 mr-2 flex-shrink-0" />
                    Desarrollo de aplicaciones web responsivas y aplicaciones móviles
                  </li>
                  <li class="flex items-center">
                    <CheckCircleIcon class="h-5 w-5 text-accent-500 mr-2 flex-shrink-0" />
                    Integración con APIs y servicios de terceros
                  </li>
                  <li class="flex items-center">
                    <CheckCircleIcon class="h-5 w-5 text-accent-500 mr-2 flex-shrink-0" />
                    Optimización de bases de datos y consultas
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Philosophy Section -->
    <section class="py-16 bg-white dark:bg-secondary-800">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12">
          <h2 class="text-3xl font-heading font-bold text-secondary-900 dark:text-white mb-4">
            Mi Filosofía
          </h2>
          <p class="text-lg text-secondary-600 dark:text-secondary-400">
            Cómo abordo los desafíos técnicos y empresariales
          </p>
        </div>
        
        <div class="grid md:grid-cols-2 gap-8">
          <div class="space-y-6">
            <h3 class="text-xl font-semibold text-secondary-900 dark:text-white">
              Enfoque Centrado en el Negocio
            </h3>
            <p class="text-secondary-700 dark:text-secondary-300">
              Cada decisión técnica debe estar alineada con los objetivos del negocio. 
              No solo construyo sistemas que funcionan, sino que creo soluciones que 
              generan valor real y medible para la organización.
            </p>
            <p class="text-secondary-700 dark:text-secondary-300">
              Mi proceso incluye un análisis profundo de los requerimientos del negocio, 
              la identificación de métricas clave y el diseño de arquitecturas que 
              permitan el crecimiento y la adaptación futura.
            </p>
          </div>
          
          <div class="space-y-6">
            <h3 class="text-xl font-semibold text-secondary-900 dark:text-white">
              Innovación Responsable
            </h3>
            <p class="text-secondary-700 dark:text-secondary-300">
              Aunque me mantengo al día con las últimas tecnologías y tendencias, 
              siempre evalúo cuidadosamente cuándo y cómo implementar nuevas soluciones. 
              La estabilidad y la confiabilidad son tan importantes como la innovación.
            </p>
            <p class="text-secondary-700 dark:text-secondary-300">
              Creo en un enfoque iterativo que permite probar nuevas tecnologías 
              de manera controlada, minimizando riesgos mientras se maximiza el aprendizaje.
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { 
  LightBulbIcon, 
  UserGroupIcon, 
  ShieldCheckIcon,
  CheckCircleIcon
} from '@heroicons/vue/24/outline'

// SEO
useHead({
  title: 'Sobre Mí - Arquitecto de Soluciones',
  meta: [
    {
      name: 'description',
      content: 'Conoce mi trayectoria profesional como Arquitecto de Soluciones, mi filosofía de trabajo y los valores que guían mi liderazgo técnico.'
    }
  ]
})
</script> 