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
          Experiencia Profesional
        </h1>
        <p class="text-xl text-white/90 max-w-3xl mx-auto">
          Trayectoria profesional marcada por el liderazgo técnico, la innovación 
          y la transformación digital de empresas
        </p>
      </div>
    </section>

    <!-- Experience Timeline -->
    <section class="py-24 bg-gradient-to-br from-gray-50 via-white to-accent-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900 relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, rgba(59, 130, 246, 0.1) 2px, transparent 2px), radial-gradient(circle at 75% 75%, rgba(147, 51, 234, 0.1) 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-20">
          <div class="inline-flex items-center px-4 py-2 bg-primary-100 dark:bg-primary-900/30 text-primary-700 dark:text-primary-300 rounded-full text-sm font-medium mb-6">
            Trayectoria Profesional
          </div>
          <h2 class="text-4xl md:text-5xl font-heading font-bold text-text-light dark:text-text-dark mb-6">
            Una Carrera de <span class="gradient-text">Innovación Constante</span>
          </h2>
          <p class="text-xl text-text-light/70 dark:text-text-dark/70 max-w-3xl mx-auto leading-relaxed">
            Más de una década liderando proyectos tecnológicos que transforman negocios y crean valor real
          </p>
        </div>

        <div class="relative">
          <!-- Timeline line -->
          <div class="absolute left-8 top-0 bottom-0 w-1 bg-gradient-tech"></div>

          <div class="space-y-16">
            <div
              v-for="(experience, index) in experiences"
              :key="index"
              class="relative flex items-start group"
            >
              <!-- Timeline dot -->
              <div class="absolute left-6 w-4 h-4 bg-gradient-tech rounded-full border-4 border-white dark:border-gray-900 shadow-tech group-hover:scale-125 transition-transform duration-300"></div>

              <!-- Content -->
              <div class="ml-16 bg-white dark:bg-gray-800 rounded-3xl shadow-soft border border-border-light dark:border-border-dark p-8 flex-1 transform hover:-translate-y-2 transition-all duration-500 relative overflow-hidden">
                <!-- Background gradient on hover -->
                <div class="absolute inset-0 bg-gradient-tech opacity-0 group-hover:opacity-5 transition-opacity duration-500"></div>
                
                <div class="relative z-10">
                  <div class="flex flex-col md:flex-row md:items-center md:justify-between mb-6">
                    <div>
                      <h3 class="text-2xl font-bold text-text-light dark:text-text-dark mb-2 group-hover:text-primary-600 dark:group-hover:text-primary-400 transition-colors">
                        {{ experience.title }}
                      </h3>
                      <p class="text-primary-600 dark:text-primary-400 font-semibold text-lg">
                        {{ experience.company }}
                      </p>
                    </div>
                    <div class="text-sm text-text-light/60 dark:text-text-dark/60 mt-2 md:mt-0 bg-gray-100 dark:bg-gray-700 px-4 py-2 rounded-full">
                      {{ experience.period }}
                    </div>
                  </div>
                  
                  <p class="text-text-light/70 dark:text-text-dark/70 leading-relaxed text-lg mb-6">
                    {{ experience.description }}
                  </p>

                  <!-- Key Achievements -->
                  <div class="mb-6">
                    <h4 class="text-lg font-semibold text-text-light dark:text-text-dark mb-4">Logros Principales:</h4>
                    <ul class="space-y-3">
                      <li
                        v-for="(achievement, idx) in experience.achievements"
                        :key="idx"
                        class="flex items-start space-x-3"
                      >
                        <div class="w-2 h-2 bg-accent-500 rounded-full mt-2 flex-shrink-0"></div>
                        <span class="text-text-light/80 dark:text-text-dark/80">{{ achievement }}</span>
                      </li>
                    </ul>
                  </div>

                  <!-- Technologies -->
                  <div class="mb-6">
                    <h4 class="text-lg font-semibold text-text-light dark:text-text-dark mb-4">Tecnologías Utilizadas:</h4>
                    <div class="flex flex-wrap gap-2">
                      <span
                        v-for="tech in experience.technologies"
                        :key="tech"
                        class="px-4 py-2 bg-accent-100 dark:bg-accent-900 text-accent-800 dark:text-accent-200 rounded-full font-medium text-sm"
                      >
                        {{ tech }}
                      </span>
                    </div>
                  </div>

                  <!-- Impact Metrics -->
                  <div class="grid md:grid-cols-3 gap-4">
                    <div
                      v-for="(metric, idx) in experience.metrics"
                      :key="idx"
                      class="p-4 bg-gradient-tech rounded-xl text-white text-center transform hover:scale-105 transition-transform duration-300"
                    >
                      <div class="text-2xl font-bold mb-1">{{ metric.value }}</div>
                      <div class="text-sm opacity-90">{{ metric.label }}</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills Evolution -->
    <section class="py-24 bg-gradient-tech relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-10">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, white 2px, transparent 2px), radial-gradient(circle at 75% 75%, white 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-heading font-bold text-white mb-6">
            Evolución de <span class="text-accent-300">Habilidades</span>
          </h2>
          <p class="text-xl text-white/80 max-w-3xl mx-auto">
            Cómo mis habilidades técnicas y de liderazgo han evolucionado a lo largo de mi carrera
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div
            v-for="(skill, index) in skillEvolution"
            :key="index"
            class="text-center group"
          >
            <div class="w-24 h-24 bg-white/10 rounded-3xl flex items-center justify-center mx-auto mb-6 group-hover:scale-110 transition-transform duration-500">
              <component :is="skill.icon" class="h-12 w-12 text-white" />
            </div>
            <h3 class="text-xl font-bold text-white mb-3">{{ skill.name }}</h3>
            <div class="space-y-2">
              <div
                v-for="(level, idx) in skill.levels"
                :key="idx"
                class="flex items-center justify-between text-sm"
              >
                <span class="text-white/80">{{ level.year }}</span>
                <div class="flex items-center space-x-2">
                  <div class="w-16 h-2 bg-white/20 rounded-full overflow-hidden">
                    <div 
                      class="h-full bg-white rounded-full transition-all duration-500"
                      :style="{ width: level.percentage + '%' }"
                    ></div>
                  </div>
                  <span class="text-white font-medium">{{ level.percentage }}%</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Career Highlights -->
    <section class="py-24 bg-gradient-to-br from-primary-50 via-white to-secondary-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900 relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-5">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, rgba(59, 130, 246, 0.1) 2px, transparent 2px), radial-gradient(circle at 75% 75%, rgba(147, 51, 234, 0.1) 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <div class="inline-flex items-center px-4 py-2 bg-primary-100 dark:bg-primary-900/30 text-primary-700 dark:text-primary-300 rounded-full text-sm font-medium mb-6">
            Momentos Destacados
          </div>
          <h2 class="text-4xl md:text-5xl font-heading font-bold text-text-light dark:text-text-dark mb-6">
            Momentos que <span class="gradient-text">Definieron mi Carrera</span>
          </h2>
          <p class="text-xl text-text-light/70 dark:text-text-dark/70 max-w-3xl mx-auto leading-relaxed">
            Proyectos y logros que han marcado hitos importantes en mi desarrollo profesional
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div
            v-for="(highlight, index) in careerHighlights"
            :key="index"
            class="group bg-white dark:bg-gray-800 rounded-3xl shadow-soft border border-border-light dark:border-border-dark p-8 hover:shadow-tech-xl transition-all duration-500 transform hover:-translate-y-3 relative overflow-hidden"
          >
            <!-- Background gradient on hover -->
            <div class="absolute inset-0 bg-gradient-tech opacity-0 group-hover:opacity-5 transition-opacity duration-500"></div>
            
            <div class="relative z-10">
              <div class="w-16 h-16 bg-gradient-tech rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-500 shadow-tech">
                <component :is="highlight.icon" class="h-8 w-8 text-white" />
              </div>
              <h3 class="text-xl font-bold text-text-light dark:text-text-dark mb-4 group-hover:text-primary-600 dark:group-hover:text-primary-400 transition-colors">
                {{ highlight.title }}
              </h3>
              <p class="text-text-light/70 dark:text-text-dark/70 leading-relaxed mb-4">
                {{ highlight.description }}
              </p>
              <div class="text-sm text-primary-600 dark:text-primary-400 font-medium">
                {{ highlight.year }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-24 bg-gradient-tech relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-10">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, white 2px, transparent 2px), radial-gradient(circle at 75% 75%, white 2px, transparent 2px); background-size: 60px 60px;"></div>
      </div>
      
      <div class="relative z-10 max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <h2 class="text-4xl md:text-5xl font-heading font-bold text-white mb-8">
          ¿Listo para <span class="text-accent-300">Trabajar Juntos</span>?
        </h2>
        <p class="text-xl text-white/80 mb-12 max-w-3xl mx-auto leading-relaxed">
          Con más de una década de experiencia en transformación digital, estoy listo para 
          llevar tu proyecto al siguiente nivel
        </p>
        <div class="flex flex-col sm:flex-row gap-6 justify-center items-center">
          <NuxtLink 
            to="/contacto"
            class="group px-12 py-5 bg-white text-primary-600 font-bold text-lg rounded-2xl hover:bg-gray-50 transform hover:-translate-y-2 transition-all duration-500 shadow-lg hover:shadow-xl"
          >
            <span>Iniciar Conversación</span>
            <ArrowRightIcon class="ml-3 h-6 w-6 group-hover:translate-x-2 transition-transform duration-300" />
          </NuxtLink>
          <NuxtLink 
            to="/proyectos"
            class="group px-12 py-5 border-2 border-white text-white font-bold text-lg rounded-2xl hover:bg-white hover:text-primary-600 transform hover:-translate-y-2 transition-all duration-500"
          >
            <span>Ver Proyectos</span>
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
  RocketLaunchIcon,
  UserGroupIcon,
  CodeBracketIcon
} from '@heroicons/vue/24/outline'

// SEO
useHead({
  title: 'Experiencia Profesional - Arquitecto de Soluciones',
  meta: [
    { name: 'description', content: 'Trayectoria profesional de más de 10 años en arquitectura de software, transformación digital y liderazgo técnico. Experiencia en proyectos enterprise.' }
  ]
})

const experiences = [
  {
    title: 'Senior Solutions Architect',
    company: 'TechCorp Solutions',
    period: '2022 - Presente',
    description: 'Lidero el diseño de arquitecturas escalables para clientes enterprise, especializándome en migraciones cloud y transformación digital. Trabajo directamente con CTOs y equipos de desarrollo para implementar soluciones que soporten el crecimiento empresarial.',
    achievements: [
      'Diseñé arquitecturas para 15+ clientes Fortune 500',
      'Reduje costos de infraestructura en un 40% promedio',
      'Implementé prácticas DevOps que aceleraron el time-to-market en 60%',
      'Lideré equipos de hasta 25 desarrolladores'
    ],
    technologies: ['AWS', 'Azure', 'Kubernetes', 'Terraform', 'Python', 'React', 'Node.js'],
    metrics: [
      { value: '15+', label: 'Clientes Enterprise' },
      { value: '40%', label: 'Reducción de Costos' },
      { value: '60%', label: 'Mejora en Velocidad' }
    ]
  },
  {
    title: 'Lead Software Engineer',
    company: 'InnovateTech',
    period: '2020 - 2022',
    description: 'Dirigí el desarrollo de plataformas de e-commerce y fintech, implementando arquitecturas de microservicios y prácticas DevOps. Fui responsable de la toma de decisiones técnicas y la mentoría de desarrolladores junior.',
    achievements: [
      'Desarrollé plataforma de e-commerce con 1M+ usuarios',
      'Implementé sistema de pagos que procesa $50M+ mensuales',
      'Reduje bugs en producción en un 70%',
      'Capacité a 12 desarrolladores en nuevas tecnologías'
    ],
    technologies: ['Node.js', 'React', 'MongoDB', 'Redis', 'Docker', 'Jenkins'],
    metrics: [
      { value: '1M+', label: 'Usuarios Activos' },
      { value: '$50M+', label: 'Procesamiento Mensual' },
      { value: '70%', label: 'Menos Bugs' }
    ]
  },
  {
    title: 'DevOps Engineer',
    company: 'CloudFirst Systems',
    period: '2018 - 2020',
    description: 'Implementé pipelines de CI/CD y automatización de infraestructura, mejorando significativamente la velocidad de entrega y la estabilidad de los sistemas. Trabajé en la migración completa de infraestructura on-premise a la nube.',
    achievements: [
      'Automaticé 100% de los despliegues',
      'Reduje tiempo de deployment de 4 horas a 15 minutos',
      'Implementé monitoreo 24/7 con 99.9% uptime',
      'Migré 50+ aplicaciones a la nube'
    ],
    technologies: ['Jenkins', 'Kubernetes', 'Terraform', 'Prometheus', 'AWS'],
    metrics: [
      { value: '100%', label: 'Automatización' },
      { value: '99.9%', label: 'Uptime' },
      { value: '50+', label: 'Apps Migradas' }
    ]
  },
  {
    title: 'Full Stack Developer',
    company: 'Digital Solutions',
    period: '2016 - 2018',
    description: 'Desarrollé aplicaciones web y móviles, adquiriendo experiencia en múltiples tecnologías y metodologías ágiles. Participé en proyectos de diferentes industrias, desde startups hasta empresas establecidas.',
    achievements: [
      'Desarrollé 20+ aplicaciones web y móviles',
      'Implementé metodologías ágiles en 5 equipos',
      'Optimicé rendimiento de aplicaciones en un 50%',
      'Contribuí a proyectos open source'
    ],
    technologies: ['JavaScript', 'React', 'Python', 'PostgreSQL', 'AWS'],
    metrics: [
      { value: '20+', label: 'Aplicaciones' },
      { value: '50%', label: 'Mejora Rendimiento' },
      { value: '5', label: 'Equipos Liderados' }
    ]
  }
]

const skillEvolution = [
  {
    name: 'Arquitectura',
    icon: CpuChipIcon,
    levels: [
      { year: '2016', percentage: 60 },
      { year: '2018', percentage: 75 },
      { year: '2020', percentage: 85 },
      { year: '2023', percentage: 95 }
    ]
  },
  {
    name: 'Cloud',
    icon: CloudIcon,
    levels: [
      { year: '2016', percentage: 40 },
      { year: '2018', percentage: 70 },
      { year: '2020', percentage: 85 },
      { year: '2023', percentage: 95 }
    ]
  },
  {
    name: 'Liderazgo',
    icon: UserGroupIcon,
    levels: [
      { year: '2016', percentage: 30 },
      { year: '2018', percentage: 50 },
      { year: '2020', percentage: 75 },
      { year: '2023', percentage: 90 }
    ]
  },
  {
    name: 'DevOps',
    icon: CogIcon,
    levels: [
      { year: '2016', percentage: 20 },
      { year: '2018', percentage: 65 },
      { year: '2020', percentage: 80 },
      { year: '2023', percentage: 90 }
    ]
  }
]

const careerHighlights = [
  {
    icon: RocketLaunchIcon,
    title: 'Primera Migración Cloud Enterprise',
    description: 'Lideré la migración completa de una empresa Fortune 500 desde infraestructura on-premise hacia AWS, estableciendo nuevos estándares en la industria.',
    year: '2020'
  },
  {
    icon: ChartBarIcon,
    title: 'Plataforma de E-commerce Escalable',
    description: 'Diseñé y desarrollé una plataforma que maneja 1M+ usuarios concurrentes, procesando transacciones por valor de $50M+ mensuales.',
    year: '2021'
  },
  {
    icon: ShieldCheckIcon,
    title: 'Implementación de Seguridad Zero Trust',
    description: 'Implementé arquitectura de seguridad Zero Trust para una institución financiera, logrando 100% de cumplimiento regulatorio.',
    year: '2022'
  },
  {
    icon: CodeBracketIcon,
    title: 'Transformación DevOps Completa',
    description: 'Transformé los procesos de desarrollo de una organización de 200+ desarrolladores, reduciendo el time-to-market en un 60%.',
    year: '2023'
  },
  {
    icon: CpuChipIcon,
    title: 'Arquitectura de Microservicios',
    description: 'Diseñé arquitectura de microservicios para una plataforma de fintech que procesa millones de transacciones diarias.',
    year: '2023'
  },
  {
    icon: UserGroupIcon,
    title: 'Liderazgo de Equipo Técnico',
    description: 'Lideré un equipo de 30+ desarrolladores en la creación de productos innovadores, implementando metodologías ágiles y cultura de innovación.',
    year: '2023'
  }
]
</script> 