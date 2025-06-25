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
          Certificaciones
        </h1>
        <p class="text-xl text-white/90 max-w-3xl mx-auto">
          Credenciales profesionales que validan mi experiencia en las tecnologías 
          más demandadas del mercado y mejores prácticas de la industria
        </p>
      </div>
    </section>

    <!-- Certifications Overview -->
    <section class="py-20 bg-gradient-to-br from-gray-50 via-white to-accent-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Stats -->
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mb-16">
          <div class="text-center group">
            <div class="text-3xl md:text-4xl font-bold text-primary-600 dark:text-primary-400 mb-2 group-hover:scale-110 transition-transform duration-300">
              {{ totalCertifications }}
            </div>
            <div class="text-text-light/70 dark:text-text-dark/70">Total Certificaciones</div>
          </div>
          <div class="text-center group">
            <div class="text-3xl md:text-4xl font-bold text-accent-600 dark:text-accent-400 mb-2 group-hover:scale-110 transition-transform duration-300">
              {{ activeCertifications }}
            </div>
            <div class="text-text-light/70 dark:text-text-dark/70">Activas</div>
          </div>
          <div class="text-center group">
            <div class="text-3xl md:text-4xl font-bold text-secondary-600 dark:text-secondary-400 mb-2 group-hover:scale-110 transition-transform duration-300">
              {{ cloudCertifications }}
            </div>
            <div class="text-text-light/70 dark:text-text-dark/70">Cloud</div>
          </div>
          <div class="text-center group">
            <div class="text-3xl md:text-4xl font-bold text-success-600 dark:text-success-400 mb-2 group-hover:scale-110 transition-transform duration-300">
              {{ securityCertifications }}
            </div>
            <div class="text-text-light/70 dark:text-text-dark/70">Seguridad</div>
          </div>
        </div>

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

        <!-- Certifications Grid -->
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div
            v-for="cert in filteredCertifications"
            :key="cert.id"
            class="group bg-white dark:bg-gray-800 rounded-2xl shadow-soft hover:shadow-tech-xl border border-border-light dark:border-border-dark overflow-hidden transition-all duration-300 transform hover:-translate-y-2 relative"
          >
            <!-- Certification Header -->
            <div class="relative h-48 bg-gradient-tech overflow-hidden">
              <div class="absolute inset-0 bg-gradient-to-br from-primary-600/20 to-secondary-600/20"></div>
              <div class="absolute inset-0 flex items-center justify-center">
                <component :is="cert.icon" class="h-16 w-16 text-white opacity-80 group-hover:scale-110 transition-transform duration-300" />
              </div>
              <div class="absolute top-4 right-4">
                <span :class="[
                  'px-3 py-1 rounded-full text-xs font-medium',
                  cert.status === 'Activa' ? 'bg-success-100 text-success-800 dark:bg-success-900 dark:text-success-200' :
                  cert.status === 'En Progreso' ? 'bg-accent-100 text-accent-800 dark:bg-accent-900 dark:text-accent-200' :
                  'bg-warning-100 text-warning-800 dark:bg-warning-900 dark:text-warning-200'
                ]">
                  {{ cert.status }}
                </span>
              </div>
            </div>

            <!-- Certification Content -->
            <div class="p-6">
              <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-3 group-hover:text-primary-600 dark:group-hover:text-primary-400 transition-colors">
                {{ cert.name }}
              </h3>
              <p class="text-text-light/70 dark:text-text-dark/70 mb-4 leading-relaxed">
                {{ cert.description }}
              </p>

              <!-- Certification Details -->
              <div class="space-y-3 mb-6">
                <div class="flex items-center justify-between">
                  <span class="text-sm text-text-light/60 dark:text-text-dark/60">Proveedor:</span>
                  <span class="text-sm font-medium text-text-light dark:text-text-dark">{{ cert.provider }}</span>
                </div>
                <div class="flex items-center justify-between">
                  <span class="text-sm text-text-light/60 dark:text-text-dark/60">Nivel:</span>
                  <span class="text-sm font-medium text-primary-600 dark:text-primary-400">{{ cert.level }}</span>
                </div>
                <div class="flex items-center justify-between">
                  <span class="text-sm text-text-light/60 dark:text-text-dark/60">Expiración:</span>
                  <span class="text-sm font-medium text-text-light dark:text-text-dark">{{ cert.expiration }}</span>
                </div>
              </div>

              <!-- Skills Covered -->
              <div class="mb-6">
                <h4 class="text-sm font-semibold text-text-light dark:text-text-dark mb-3">Habilidades Cubiertas:</h4>
                <div class="flex flex-wrap gap-2">
                  <span
                    v-for="skill in cert.skills"
                    :key="skill"
                    class="px-2 py-1 bg-accent-100 dark:bg-accent-900 text-accent-800 dark:text-accent-200 text-xs rounded-full"
                  >
                    {{ skill }}
                  </span>
                </div>
              </div>

              <!-- CTA Button -->
              <button
                @click="showCertificationDetails(cert)"
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

    <!-- Certification Details Modal -->
    <div
      v-if="selectedCertification"
      class="fixed inset-0 bg-black/50 backdrop-blur-sm z-50 flex items-center justify-center p-4"
      @click="selectedCertification = null"
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
                {{ selectedCertification.name }}
              </h2>
              <p class="text-text-light/70 dark:text-text-dark/70">
                {{ selectedCertification.provider }} • {{ selectedCertification.level }}
              </p>
            </div>
            <button
              @click="selectedCertification = null"
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
                {{ selectedCertification.fullDescription }}
              </p>
            </div>

            <div class="grid md:grid-cols-2 gap-6">
              <div>
                <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-3">
                  Detalles del Examen
                </h3>
                <div class="space-y-3">
                  <div class="flex justify-between">
                    <span class="text-text-light/70 dark:text-text-dark/70">Duración:</span>
                    <span class="font-medium">{{ selectedCertification.examDuration }}</span>
                  </div>
                  <div class="flex justify-between">
                    <span class="text-text-light/70 dark:text-text-dark/70">Preguntas:</span>
                    <span class="font-medium">{{ selectedCertification.examQuestions }}</span>
                  </div>
                  <div class="flex justify-between">
                    <span class="text-text-light/70 dark:text-text-dark/70">Puntuación:</span>
                    <span class="font-medium">{{ selectedCertification.passingScore }}</span>
                  </div>
                  <div class="flex justify-between">
                    <span class="text-text-light/70 dark:text-text-dark/70">Costo:</span>
                    <span class="font-medium">{{ selectedCertification.cost }}</span>
                  </div>
                </div>
              </div>

              <div>
                <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-3">
                  Beneficios
                </h3>
                <ul class="space-y-2">
                  <li
                    v-for="(benefit, index) in selectedCertification.benefits"
                    :key="index"
                    class="flex items-start space-x-3"
                  >
                    <div class="w-2 h-2 bg-accent-500 rounded-full mt-2 flex-shrink-0"></div>
                    <span class="text-text-light/80 dark:text-text-dark/80">{{ benefit }}</span>
                  </li>
                </ul>
              </div>
            </div>

            <div>
              <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-3">
                Habilidades Cubiertas
              </h3>
              <div class="flex flex-wrap gap-2">
                <span
                  v-for="skill in selectedCertification.skills"
                  :key="skill"
                  class="px-4 py-2 bg-accent-100 dark:bg-accent-900 text-accent-800 dark:text-accent-200 rounded-full font-medium"
                >
                  {{ skill }}
                </span>
              </div>
            </div>

            <div class="bg-gradient-tech rounded-xl p-6 text-white">
              <h3 class="text-xl font-semibold mb-3">¿Interesado en esta certificación?</h3>
              <p class="mb-4 opacity-90">
                Puedo ayudarte a prepararte para esta certificación o compartir mi experiencia en el proceso de estudio.
              </p>
              <NuxtLink 
                to="/contacto"
                class="inline-flex items-center px-6 py-3 bg-white text-primary-600 font-semibold rounded-xl hover:bg-gray-50 transform hover:-translate-y-1 transition-all duration-300"
              >
                Contactar
                <ArrowRightIcon class="ml-2 h-5 w-5" />
              </NuxtLink>
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
  ShieldCheckIcon,
  CogIcon,
  ChartBarIcon,
  XMarkIcon,
  ArrowRightIcon
} from '@heroicons/vue/24/outline'

// SEO
useHead({
  title: 'Certificaciones - Arquitecto de Soluciones',
  meta: [
    { name: 'description', content: 'Certificaciones profesionales en cloud computing, seguridad, DevOps y arquitectura de software. Credenciales que validan experiencia técnica.' }
  ]
})

const activeCategory = ref('all')
const selectedCertification = ref(null)

const categories = [
  { id: 'all', name: 'Todas' },
  { id: 'cloud', name: 'Cloud' },
  { id: 'security', name: 'Seguridad' },
  { id: 'devops', name: 'DevOps' },
  { id: 'architecture', name: 'Arquitectura' }
]

const certifications = [
  {
    id: 1,
    name: 'AWS Solutions Architect Professional',
    description: 'Certificación avanzada en diseño de arquitecturas escalables en AWS',
    fullDescription: 'Esta certificación valida la capacidad de diseñar e implementar aplicaciones distribuidas en AWS. Cubre temas como alta disponibilidad, escalabilidad, seguridad y costos optimizados.',
    provider: 'Amazon Web Services',
    level: 'Professional',
    status: 'Activa',
    expiration: 'Diciembre 2025',
    examDuration: '180 minutos',
    examQuestions: '75 preguntas',
    passingScore: '750/1000',
    cost: '$300 USD',
    skills: ['EC2', 'S3', 'RDS', 'Lambda', 'CloudFormation', 'VPC'],
    benefits: [
      'Reconocimiento global en la industria cloud',
      'Mayor credibilidad con clientes enterprise',
      'Acceso a recursos exclusivos de AWS',
      'Mejores oportunidades laborales'
    ],
    icon: CloudIcon,
    category: 'Cloud'
  },
  {
    id: 2,
    name: 'Azure Solutions Architect Expert',
    description: 'Experto en diseño de soluciones en Microsoft Azure',
    fullDescription: 'Certificación que demuestra experiencia en el diseño de soluciones que se ejecutan en Microsoft Azure. Incluye aspectos de computación, red, almacenamiento y seguridad.',
    provider: 'Microsoft',
    level: 'Expert',
    status: 'Activa',
    expiration: 'Marzo 2025',
    examDuration: '150 minutos',
    examQuestions: '60 preguntas',
    passingScore: '700/1000',
    cost: '$165 USD',
    skills: ['Azure VM', 'App Service', 'AKS', 'Cosmos DB', 'Azure Functions'],
    benefits: [
      'Certificación premium de Microsoft',
      'Validación de habilidades enterprise',
      'Acceso a comunidad de expertos',
      'Reconocimiento en el ecosistema Azure'
    ],
    icon: CloudIcon,
    category: 'Cloud'
  },
  {
    id: 3,
    name: 'Certified Kubernetes Administrator (CKA)',
    description: 'Administración avanzada de clusters Kubernetes',
    fullDescription: 'Certificación práctica que valida las habilidades para administrar clusters Kubernetes en producción. Incluye instalación, configuración, troubleshooting y seguridad.',
    provider: 'Cloud Native Computing Foundation',
    level: 'Advanced',
    status: 'Activa',
    expiration: 'Agosto 2025',
    examDuration: '120 minutos',
    examQuestions: 'Práctica',
    passingScore: '66%',
    cost: '$375 USD',
    skills: ['Kubernetes', 'Docker', 'Helm', 'Istio', 'Prometheus'],
    benefits: [
      'Certificación práctica y reconocida',
      'Validación de habilidades hands-on',
      'Relevante para roles DevOps/SRE',
      'Comunidad activa de profesionales'
    ],
    icon: CogIcon,
    category: 'DevOps'
  },
  {
    id: 4,
    name: 'CISSP - Certified Information Systems Security Professional',
    description: 'Seguridad de sistemas de información a nivel profesional',
    fullDescription: 'Certificación líder en seguridad de la información que cubre ocho dominios de seguridad, incluyendo gestión de riesgos, arquitectura de seguridad y operaciones de seguridad.',
    provider: 'ISC²',
    level: 'Professional',
    status: 'Activa',
    expiration: 'Enero 2026',
    examDuration: '240 minutos',
    examQuestions: '150 preguntas',
    passingScore: '700/1000',
    cost: '$749 USD',
    skills: ['Security Architecture', 'Risk Management', 'Cryptography', 'Access Control'],
    benefits: [
      'Certificación de seguridad más reconocida',
      'Requisito para roles de seguridad senior',
      'Credibilidad en auditorías y compliance',
      'Red profesional global'
    ],
    icon: ShieldCheckIcon,
    category: 'Security'
  },
  {
    id: 5,
    name: 'Google Cloud Professional Cloud Architect',
    description: 'Arquitectura de soluciones en Google Cloud Platform',
    fullDescription: 'Certificación que valida la capacidad de diseñar, desarrollar y administrar soluciones robustas, seguras, escalables y dinámicas en Google Cloud Platform.',
    provider: 'Google',
    level: 'Professional',
    status: 'Activa',
    expiration: 'Mayo 2025',
    examDuration: '120 minutos',
    examQuestions: '50 preguntas',
    passingScore: '70%',
    cost: '$200 USD',
    skills: ['GCP', 'BigQuery', 'Cloud Functions', 'GKE', 'Cloud Storage'],
    benefits: [
      'Certificación de Google Cloud',
      'Enfoque en arquitectura moderna',
      'Integración con servicios de IA/ML',
      'Crecimiento rápido del mercado'
    ],
    icon: CloudIcon,
    category: 'Cloud'
  },
  {
    id: 6,
    name: 'TOGAF 9.2 Certified',
    description: 'Arquitectura empresarial con framework TOGAF',
    fullDescription: 'Certificación en el framework de arquitectura empresarial más utilizado a nivel mundial. Cubre metodologías para el desarrollo de arquitecturas empresariales.',
    provider: 'The Open Group',
    level: 'Foundation',
    status: 'Activa',
    expiration: 'Permanente',
    examDuration: '60 minutos',
    examQuestions: '40 preguntas',
    passingScore: '55%',
    cost: '$320 USD',
    skills: ['Enterprise Architecture', 'TOGAF ADM', 'Business Architecture', 'Technology Architecture'],
    benefits: [
      'Framework de arquitectura estándar',
      'Aplicable a cualquier industria',
      'Metodología estructurada',
      'Reconocimiento internacional'
    ],
    icon: ChartBarIcon,
    category: 'Architecture'
  }
]

const filteredCertifications = computed(() => {
  if (activeCategory.value === 'all') {
    return certifications
  }
  return certifications.filter(cert => cert.category.toLowerCase() === activeCategory.value)
})

const totalCertifications = computed(() => certifications.length)
const activeCertifications = computed(() => certifications.filter(cert => cert.status === 'Activa').length)
const cloudCertifications = computed(() => certifications.filter(cert => cert.category === 'Cloud').length)
const securityCertifications = computed(() => certifications.filter(cert => cert.category === 'Security').length)

const showCertificationDetails = (certification) => {
  selectedCertification.value = certification
}
</script> 