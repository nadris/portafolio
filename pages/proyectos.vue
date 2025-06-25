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
          Proyectos Técnicos
        </h1>
        <p class="text-xl text-white/90 max-w-3xl mx-auto">
          Casos de éxito que demuestran mi experiencia en arquitectura de software, 
          transformación digital y liderazgo técnico
        </p>
      </div>
    </section>

    <!-- Projects Grid -->
    <section class="py-20 bg-gradient-to-br from-gray-50 via-white to-accent-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Filter Tabs -->
        <div class="flex flex-wrap justify-center gap-4 mb-12">
          <button
            v-for="category in categories"
            :key="category.id"
            @click="activeCategory = category.id"
            :class="[
              'group px-6 py-3 rounded-xl font-medium transition-all duration-300 relative overflow-hidden',
              activeCategory === category.id
                ? 'bg-gradient-tech text-white shadow-tech transform -translate-y-0.5'
                : 'bg-white dark:bg-gray-800 text-text-light dark:text-text-dark hover:bg-gradient-tech hover:text-white hover:shadow-tech hover:-translate-y-0.5 border border-border-light dark:border-border-dark'
            ]"
          >
            <span class="relative z-10">{{ category.name }}</span>
            <div v-if="activeCategory !== category.id" class="absolute inset-0 bg-gradient-tech opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          </button>
        </div>

        <!-- Projects Grid -->
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div
            v-for="project in filteredProjects"
            :key="project.id"
            class="group bg-white dark:bg-gray-800 rounded-2xl shadow-soft hover:shadow-tech-xl border border-border-light dark:border-border-dark overflow-hidden transition-all duration-300 transform hover:-translate-y-2 relative"
          >
            <!-- Project Image -->
            <div class="relative h-48 bg-gradient-tech overflow-hidden">
              <div class="absolute inset-0 bg-gradient-to-br from-primary-600/20 to-secondary-600/20"></div>
              <div class="absolute inset-0 flex items-center justify-center">
                <component :is="project.icon" class="h-16 w-16 text-white opacity-80 group-hover:scale-110 transition-transform duration-300" />
              </div>
              <div class="absolute top-4 right-4">
                <span :class="[
                  'px-3 py-1 rounded-full text-xs font-medium',
                  project.status === 'Completado' ? 'bg-success-100 text-success-800 dark:bg-success-900 dark:text-success-200' :
                  project.status === 'En Progreso' ? 'bg-accent-100 text-accent-800 dark:bg-accent-900 dark:text-accent-200' :
                  'bg-warning-100 text-warning-800 dark:bg-warning-900 dark:text-warning-200'
                ]">
                  {{ project.status }}
                </span>
              </div>
            </div>

            <!-- Project Content -->
            <div class="p-6">
              <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-3 group-hover:text-primary-600 dark:group-hover:text-primary-400 transition-colors">
                {{ project.title }}
              </h3>
              <p class="text-text-light/70 dark:text-text-dark/70 mb-4 leading-relaxed">
                {{ project.description }}
              </p>

              <!-- Technologies -->
              <div class="flex flex-wrap gap-2 mb-6">
                <span
                  v-for="tech in project.technologies"
                  :key="tech"
                  class="px-3 py-1 bg-accent-100 dark:bg-accent-900 text-accent-800 dark:text-accent-200 text-sm rounded-full font-medium"
                >
                  {{ tech }}
                </span>
              </div>

              <!-- Project Stats -->
              <div class="grid grid-cols-2 gap-4 mb-6">
                <div class="text-center">
                  <div class="text-lg font-semibold text-primary-600 dark:text-primary-400">
                    {{ project.duration }}
                  </div>
                  <div class="text-sm text-text-light/60 dark:text-text-dark/60">Duración</div>
                </div>
                <div class="text-center">
                  <div class="text-lg font-semibold text-primary-600 dark:text-primary-400">
                    {{ project.team }}
                  </div>
                  <div class="text-sm text-text-light/60 dark:text-text-dark/60">Equipo</div>
                </div>
              </div>

              <!-- CTA Button -->
              <button
                @click="showProjectDetails(project)"
                class="group w-full px-6 py-3 bg-gradient-tech text-white font-semibold rounded-xl hover:shadow-tech transform hover:-translate-y-1 transition-all duration-300 relative overflow-hidden"
              >
                <span class="relative z-10">Ver Detalles</span>
                <div class="absolute inset-0 bg-gradient-tech-reverse opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Project Details Modal -->
    <div
      v-if="selectedProject"
      class="fixed inset-0 bg-black/50 backdrop-blur-sm z-50 flex items-center justify-center p-4"
      @click="selectedProject = null"
    >
      <div
        class="bg-white dark:bg-gray-800 rounded-2xl max-w-4xl w-full max-h-[90vh] overflow-y-auto"
        @click.stop
      >
        <div class="p-8">
          <!-- Header -->
          <div class="flex justify-between items-start mb-6">
            <div>
              <h2 class="text-3xl font-heading font-bold text-text-light dark:text-text-dark mb-2">
                {{ selectedProject.title }}
              </h2>
              <p class="text-text-light/70 dark:text-text-dark/70">
                {{ selectedProject.category }}
              </p>
            </div>
            <button
              @click="selectedProject = null"
              class="p-2 rounded-xl bg-gradient-tech text-white hover:shadow-tech transform hover:-translate-y-0.5 transition-all duration-300"
            >
              <XMarkIcon class="h-6 w-6" />
            </button>
          </div>

          <!-- Content -->
          <div class="space-y-6">
            <div>
              <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-3">
                Descripción
              </h3>
              <p class="text-text-light/80 dark:text-text-dark/80 leading-relaxed">
                {{ selectedProject.fullDescription }}
              </p>
            </div>

            <div>
              <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-3">
                Desafíos y Soluciones
              </h3>
              <ul class="space-y-2">
                <li
                  v-for="(challenge, index) in selectedProject.challenges"
                  :key="index"
                  class="flex items-start space-x-3"
                >
                  <div class="w-2 h-2 bg-accent-500 rounded-full mt-2 flex-shrink-0"></div>
                  <span class="text-text-light/80 dark:text-text-dark/80">{{ challenge }}</span>
                </li>
              </ul>
            </div>

            <div>
              <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-3">
                Resultados
              </h3>
              <div class="grid md:grid-cols-3 gap-4">
                <div
                  v-for="(result, index) in selectedProject.results"
                  :key="index"
                  class="p-4 bg-gradient-tech rounded-xl text-white text-center transform hover:scale-105 transition-transform duration-300"
                >
                  <div class="text-2xl font-bold mb-1">{{ result.value }}</div>
                  <div class="text-sm opacity-90">{{ result.label }}</div>
                </div>
              </div>
            </div>

            <div>
              <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-3">
                Tecnologías Utilizadas
              </h3>
              <div class="flex flex-wrap gap-2">
                <span
                  v-for="tech in selectedProject.technologies"
                  :key="tech"
                  class="px-4 py-2 bg-accent-100 dark:bg-accent-900 text-accent-800 dark:text-accent-200 rounded-full font-medium"
                >
                  {{ tech }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  CloudIcon,
  CpuChipIcon,
  ChartBarIcon,
  CogIcon,
  ShieldCheckIcon,
  RocketLaunchIcon,
  XMarkIcon
} from '@heroicons/vue/24/outline'

// SEO
useHead({
  title: 'Proyectos Técnicos - Arquitecto de Soluciones',
  meta: [
    { name: 'description', content: 'Portafolio de proyectos técnicos exitosos en arquitectura de software, cloud computing, transformación digital y liderazgo técnico.' }
  ]
})

const activeCategory = ref('all')
const selectedProject = ref(null)

const categories = [
  { id: 'all', name: 'Todos' },
  { id: 'architecture', name: 'Arquitectura' },
  { id: 'cloud', name: 'Cloud' },
  { id: 'transformation', name: 'Transformación' },
  { id: 'leadership', name: 'Liderazgo' }
]

const projects = [
  {
    id: 1,
    title: 'Plataforma E-commerce Escalable',
    description: 'Arquitectura microservicios para marketplace con 1M+ usuarios',
    fullDescription: 'Diseño e implementación de una plataforma de e-commerce completamente escalable utilizando arquitectura de microservicios. La solución incluye gestión de inventario en tiempo real, procesamiento de pagos seguro, y un sistema de recomendaciones basado en IA.',
    category: 'Arquitectura',
    status: 'Completado',
    duration: '8 meses',
    team: '12 personas',
    technologies: ['Node.js', 'React', 'MongoDB', 'Redis', 'AWS', 'Docker'],
    icon: CpuChipIcon,
    challenges: [
      'Manejo de picos de tráfico durante eventos de venta',
      'Integración con múltiples proveedores de pago',
      'Optimización de rendimiento para búsquedas complejas',
      'Implementación de sistema de recomendaciones en tiempo real'
    ],
    results: [
      { value: '300%', label: 'Mejora en rendimiento' },
      { value: '99.9%', label: 'Uptime' },
      { value: '50%', label: 'Reducción de costos' }
    ]
  },
  {
    id: 2,
    title: 'Migración Cloud Enterprise',
    description: 'Migración completa de infraestructura on-premise a AWS',
    fullDescription: 'Lideré la migración completa de la infraestructura de una empresa Fortune 500 desde centros de datos on-premise hacia AWS. El proyecto incluyó la modernización de aplicaciones legacy y la implementación de prácticas DevOps.',
    category: 'Cloud',
    status: 'Completado',
    duration: '18 meses',
    team: '25 personas',
    technologies: ['AWS', 'Terraform', 'Kubernetes', 'Jenkins', 'Python'],
    icon: CloudIcon,
    challenges: [
      'Migración de aplicaciones legacy sin tiempo de inactividad',
      'Cumplimiento de regulaciones de seguridad y compliance',
      'Capacitación del equipo en nuevas tecnologías',
      'Optimización de costos en la nube'
    ],
    results: [
      { value: '40%', label: 'Reducción de costos' },
      { value: '60%', label: 'Mejora en velocidad de despliegue' },
      { value: '100%', label: 'Cumplimiento de SLA' }
    ]
  },
  {
    id: 3,
    title: 'Sistema de Analytics Avanzado',
    description: 'Plataforma de business intelligence con machine learning',
    fullDescription: 'Desarrollo de una plataforma integral de analytics que procesa petabytes de datos en tiempo real. Incluye dashboards interactivos, alertas automáticas y modelos de machine learning para predicciones empresariales.',
    category: 'Arquitectura',
    status: 'En Progreso',
    duration: '12 meses',
    team: '15 personas',
    technologies: ['Python', 'Apache Spark', 'Kafka', 'Elasticsearch', 'React'],
    icon: ChartBarIcon,
    challenges: [
      'Procesamiento de datos en tiempo real a gran escala',
      'Integración de múltiples fuentes de datos',
      'Desarrollo de modelos de ML precisos',
      'Creación de dashboards intuitivos para usuarios no técnicos'
    ],
    results: [
      { value: '5x', label: 'Velocidad de procesamiento' },
      { value: '95%', label: 'Precisión de predicciones' },
      { value: '80%', label: 'Reducción en tiempo de análisis' }
    ]
  },
  {
    id: 4,
    title: 'Transformación DevOps',
    description: 'Implementación de CI/CD y automatización completa',
    fullDescription: 'Transformación completa de los procesos de desarrollo e implementación de una organización de 200+ desarrolladores. Implementación de pipelines automatizados, monitoreo proactivo y cultura DevOps.',
    category: 'Transformación',
    status: 'Completado',
    duration: '10 meses',
    team: '8 personas',
    technologies: ['Jenkins', 'Docker', 'Kubernetes', 'Prometheus', 'Grafana'],
    icon: CogIcon,
    challenges: [
      'Cambio cultural en equipos tradicionales',
      'Integración con herramientas legacy',
      'Implementación de monitoreo 24/7',
      'Capacitación masiva del equipo'
    ],
    results: [
      { value: '90%', label: 'Reducción en tiempo de despliegue' },
      { value: '70%', label: 'Menos errores en producción' },
      { value: '24/7', label: 'Monitoreo automático' }
    ]
  },
  {
    id: 5,
    title: 'Arquitectura de Seguridad Zero Trust',
    description: 'Implementación de seguridad avanzada para empresa financiera',
    fullDescription: 'Diseño e implementación de una arquitectura de seguridad Zero Trust para una institución financiera. Incluye autenticación multifactor, segmentación de red, y monitoreo de amenazas en tiempo real.',
    category: 'Arquitectura',
    status: 'Completado',
    duration: '14 meses',
    team: '10 personas',
    technologies: ['Okta', 'CrowdStrike', 'Palo Alto', 'Splunk', 'AWS IAM'],
    icon: ShieldCheckIcon,
    challenges: [
      'Implementación sin interrumpir operaciones críticas',
      'Cumplimiento de regulaciones financieras',
      'Integración con sistemas legacy',
      'Capacitación de usuarios en nuevas prácticas'
    ],
    results: [
      { value: '99.9%', label: 'Tiempo de detección de amenazas' },
      { value: '0', label: 'Incidentes de seguridad' },
      { value: '100%', label: 'Cumplimiento regulatorio' }
    ]
  },
  {
    id: 6,
    title: 'Liderazgo de Equipo Técnico',
    description: 'Gestión y mentoría de equipo de 30+ desarrolladores',
    fullDescription: 'Lideré un equipo de 30+ desarrolladores en la creación de productos innovadores. Implementé metodologías ágiles, programas de mentoría técnica, y procesos de toma de decisiones basados en datos.',
    category: 'Liderazgo',
    status: 'En Progreso',
    duration: 'Ongoing',
    team: '30 personas',
    technologies: ['Agile', 'Scrum', 'JIRA', 'Confluence', 'Git'],
    icon: RocketLaunchIcon,
    challenges: [
      'Escalar el equipo manteniendo la calidad del código',
      'Implementar cultura de innovación y experimentación',
      'Balancear velocidad de entrega con estabilidad',
      'Desarrollar talento técnico interno'
    ],
    results: [
      { value: '200%', label: 'Productividad del equipo' },
      { value: '85%', label: 'Satisfacción del empleado' },
      { value: '15', label: 'Promociones internas' }
    ]
  }
]

const filteredProjects = computed(() => {
  if (activeCategory.value === 'all') {
    return projects
  }
  return projects.filter(project => {
    const categoryMap = {
      'architecture': 'Arquitectura',
      'cloud': 'Cloud',
      'transformation': 'Transformación',
      'leadership': 'Liderazgo'
    }
    return project.category === categoryMap[activeCategory.value]
  })
})

const showProjectDetails = (project) => {
  selectedProject.value = project
}
</script> 