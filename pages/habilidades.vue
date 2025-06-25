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
          Habilidades Técnicas
        </h1>
        <p class="text-xl text-white/90 max-w-3xl mx-auto">
          Experiencia en las tecnologías y metodologías más demandadas del mercado, 
          con enfoque en arquitecturas escalables y transformación digital
        </p>
      </div>
    </section>

    <!-- Skills Overview -->
    <section class="py-20 bg-gradient-to-br from-gray-50 via-white to-accent-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Skill Categories -->
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8 mb-16">
          <div
            v-for="(category, index) in skillCategories"
            :key="index"
            class="text-center group"
          >
            <div class="w-20 h-20 bg-gradient-tech rounded-2xl flex items-center justify-center mx-auto mb-4 group-hover:scale-110 transition-transform duration-300 shadow-tech">
              <component :is="category.icon" class="h-10 w-10 text-white" />
            </div>
            <h3 class="text-xl font-semibold text-text-light dark:text-text-dark mb-2">
              {{ category.name }}
            </h3>
            <p class="text-text-light/70 dark:text-text-dark/70">
              {{ category.description }}
            </p>
          </div>
        </div>

        <!-- Detailed Skills -->
        <div class="space-y-16">
          <!-- Cloud & Infrastructure -->
          <div class="bg-white dark:bg-gray-800 rounded-2xl shadow-soft border border-border-light dark:border-border-dark p-8 relative overflow-hidden">
            <div class="absolute inset-0 bg-gradient-tech opacity-5"></div>
            <div class="relative z-10">
              <div class="flex items-center mb-8">
                <div class="w-12 h-12 bg-gradient-tech rounded-xl flex items-center justify-center mr-4 shadow-tech">
                  <CloudIcon class="h-6 w-6 text-white" />
                </div>
                <div>
                  <h2 class="text-2xl font-heading font-bold text-text-light dark:text-text-dark">
                    Cloud & Infrastructure
                  </h2>
                  <p class="text-text-light/70 dark:text-text-dark/70">
                    Experiencia en las principales plataformas cloud y herramientas de infraestructura
                  </p>
                </div>
              </div>

              <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div
                  v-for="skill in cloudSkills"
                  :key="skill.name"
                  class="group p-6 bg-gray-50 dark:bg-gray-700 rounded-xl hover:bg-gradient-tech hover:shadow-tech transition-all duration-300 transform hover:-translate-y-1"
                >
                  <div class="flex items-center justify-between mb-3">
                    <h3 class="font-semibold text-text-light dark:text-text-dark group-hover:text-white transition-colors">
                      {{ skill.name }}
                    </h3>
                    <div class="text-sm font-medium text-primary-600 dark:text-primary-400 group-hover:text-white transition-colors">
                      {{ skill.level }}
                    </div>
                  </div>
                  <div class="w-full bg-gray-200 dark:bg-gray-600 rounded-full h-2 mb-3">
                    <div 
                      class="bg-gradient-tech h-2 rounded-full transition-all duration-500"
                      :style="{ width: skill.percentage + '%' }"
                    ></div>
                  </div>
                  <p class="text-sm text-text-light/70 dark:text-text-dark/70 group-hover:text-white/80 transition-colors">
                    {{ skill.description }}
                  </p>
                </div>
              </div>
            </div>
          </div>

          <!-- Programming & Frameworks -->
          <div class="bg-white dark:bg-gray-800 rounded-2xl shadow-soft border border-border-light dark:border-border-dark p-8 relative overflow-hidden">
            <div class="absolute inset-0 bg-gradient-tech opacity-5"></div>
            <div class="relative z-10">
              <div class="flex items-center mb-8">
                <div class="w-12 h-12 bg-gradient-tech rounded-xl flex items-center justify-center mr-4 shadow-tech">
                  <CodeBracketIcon class="h-6 w-6 text-white" />
                </div>
                <div>
                  <h2 class="text-2xl font-heading font-bold text-text-light dark:text-text-dark">
                    Programming & Frameworks
                  </h2>
                  <p class="text-text-light/70 dark:text-text-dark/70">
                    Lenguajes de programación y frameworks para desarrollo moderno
                  </p>
                </div>
              </div>

              <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div
                  v-for="skill in programmingSkills"
                  :key="skill.name"
                  class="group p-6 bg-gray-50 dark:bg-gray-700 rounded-xl hover:bg-gradient-tech hover:shadow-tech transition-all duration-300 transform hover:-translate-y-1"
                >
                  <div class="flex items-center justify-between mb-3">
                    <h3 class="font-semibold text-text-light dark:text-text-dark group-hover:text-white transition-colors">
                      {{ skill.name }}
                    </h3>
                    <div class="text-sm font-medium text-primary-600 dark:text-primary-400 group-hover:text-white transition-colors">
                      {{ skill.level }}
                    </div>
                  </div>
                  <div class="w-full bg-gray-200 dark:bg-gray-600 rounded-full h-2 mb-3">
                    <div 
                      class="bg-gradient-tech h-2 rounded-full transition-all duration-500"
                      :style="{ width: skill.percentage + '%' }"
                    ></div>
                  </div>
                  <p class="text-sm text-text-light/70 dark:text-text-dark/70 group-hover:text-white/80 transition-colors">
                    {{ skill.description }}
                  </p>
                </div>
              </div>
            </div>
          </div>

          <!-- DevOps & Tools -->
          <div class="bg-white dark:bg-gray-800 rounded-2xl shadow-soft border border-border-light dark:border-border-dark p-8 relative overflow-hidden">
            <div class="absolute inset-0 bg-gradient-tech opacity-5"></div>
            <div class="relative z-10">
              <div class="flex items-center mb-8">
                <div class="w-12 h-12 bg-gradient-tech rounded-xl flex items-center justify-center mr-4 shadow-tech">
                  <CogIcon class="h-6 w-6 text-white" />
                </div>
                <div>
                  <h2 class="text-2xl font-heading font-bold text-text-light dark:text-text-dark">
                    DevOps & Tools
                  </h2>
                  <p class="text-text-light/70 dark:text-text-dark/70">
                    Herramientas y prácticas para automatización y entrega continua
                  </p>
                </div>
              </div>

              <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div
                  v-for="skill in devopsSkills"
                  :key="skill.name"
                  class="group p-6 bg-gray-50 dark:bg-gray-700 rounded-xl hover:bg-gradient-tech hover:shadow-tech transition-all duration-300 transform hover:-translate-y-1"
                >
                  <div class="flex items-center justify-between mb-3">
                    <h3 class="font-semibold text-text-light dark:text-text-dark group-hover:text-white transition-colors">
                      {{ skill.name }}
                    </h3>
                    <div class="text-sm font-medium text-primary-600 dark:text-primary-400 group-hover:text-white transition-colors">
                      {{ skill.level }}
                    </div>
                  </div>
                  <div class="w-full bg-gray-200 dark:bg-gray-600 rounded-full h-2 mb-3">
                    <div 
                      class="bg-gradient-tech h-2 rounded-full transition-all duration-500"
                      :style="{ width: skill.percentage + '%' }"
                    ></div>
                  </div>
                  <p class="text-sm text-text-light/70 dark:text-text-dark/70 group-hover:text-white/80 transition-colors">
                    {{ skill.description }}
                  </p>
                </div>
              </div>
            </div>
          </div>

          <!-- Soft Skills -->
          <div class="bg-white dark:bg-gray-800 rounded-2xl shadow-soft border border-border-light dark:border-border-dark p-8 relative overflow-hidden">
            <div class="absolute inset-0 bg-gradient-tech opacity-5"></div>
            <div class="relative z-10">
              <div class="flex items-center mb-8">
                <div class="w-12 h-12 bg-gradient-tech rounded-xl flex items-center justify-center mr-4 shadow-tech">
                  <UserGroupIcon class="h-6 w-6 text-white" />
                </div>
                <div>
                  <h2 class="text-2xl font-heading font-bold text-text-light dark:text-text-dark">
                    Soft Skills & Leadership
                  </h2>
                  <p class="text-text-light/70 dark:text-text-dark/70">
                    Habilidades de liderazgo, comunicación y gestión de equipos
                  </p>
                </div>
              </div>

              <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div
                  v-for="skill in softSkills"
                  :key="skill.name"
                  class="group p-6 bg-gray-50 dark:bg-gray-700 rounded-xl hover:bg-gradient-tech hover:shadow-tech transition-all duration-300 transform hover:-translate-y-1"
                >
                  <div class="flex items-center justify-between mb-3">
                    <h3 class="font-semibold text-text-light dark:text-text-dark group-hover:text-white transition-colors">
                      {{ skill.name }}
                    </h3>
                    <div class="text-sm font-medium text-primary-600 dark:text-primary-400 group-hover:text-white transition-colors">
                      {{ skill.level }}
                    </div>
                  </div>
                  <div class="w-full bg-gray-200 dark:bg-gray-600 rounded-full h-2 mb-3">
                    <div 
                      class="bg-gradient-tech h-2 rounded-full transition-all duration-500"
                      :style="{ width: skill.percentage + '%' }"
                    ></div>
                  </div>
                  <p class="text-sm text-text-light/70 dark:text-text-dark/70 group-hover:text-white/80 transition-colors">
                    {{ skill.description }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Experience Timeline -->
    <section class="py-20 bg-gradient-tech relative overflow-hidden">
      <!-- Background pattern -->
      <div class="absolute inset-0 opacity-10">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 25% 25%, white 2px, transparent 2px), radial-gradient(circle at 75% 75%, white 2px, transparent 2px); background-size: 50px 50px;"></div>
      </div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-3xl md:text-4xl font-heading font-bold text-white mb-4">
            Experiencia Profesional
          </h2>
          <p class="text-lg text-white/80 max-w-2xl mx-auto">
            Trayectoria profesional marcada por el liderazgo técnico y la innovación
          </p>
        </div>

        <div class="relative">
          <!-- Timeline line -->
          <div class="absolute left-8 top-0 bottom-0 w-0.5 bg-white/30"></div>

          <div class="space-y-12">
            <div
              v-for="(experience, index) in experiences"
              :key="index"
              class="relative flex items-start"
            >
              <!-- Timeline dot -->
              <div class="absolute left-6 w-4 h-4 bg-gradient-tech rounded-full border-4 border-white shadow-tech"></div>

              <!-- Content -->
              <div class="ml-16 bg-white dark:bg-gray-800 rounded-2xl shadow-soft border border-white/20 p-6 flex-1 transform hover:-translate-y-1 transition-transform duration-300">
                <div class="flex flex-col md:flex-row md:items-center md:justify-between mb-4">
                  <div>
                    <h3 class="text-xl font-semibold text-text-light dark:text-text-dark">
                      {{ experience.title }}
                    </h3>
                    <p class="text-primary-600 dark:text-primary-400 font-medium">
                      {{ experience.company }}
                    </p>
                  </div>
                  <div class="text-sm text-text-light/60 dark:text-text-dark/60 mt-2 md:mt-0">
                    {{ experience.period }}
                  </div>
                </div>
                <p class="text-text-light/70 dark:text-text-dark/70 mb-4">
                  {{ experience.description }}
                </p>
                <div class="flex flex-wrap gap-2">
                  <span
                    v-for="tech in experience.technologies"
                    :key="tech"
                    class="px-3 py-1 bg-accent-100 dark:bg-accent-900 text-accent-800 dark:text-accent-200 text-sm rounded-full font-medium"
                  >
                    {{ tech }}
                  </span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import {
  CloudIcon,
  CodeBracketIcon,
  CogIcon,
  UserGroupIcon,
  CpuChipIcon,
  ChartBarIcon,
  ShieldCheckIcon,
  RocketLaunchIcon
} from '@heroicons/vue/24/outline'

// SEO
useHead({
  title: 'Habilidades Técnicas - Arquitecto de Soluciones',
  meta: [
    { name: 'description', content: 'Habilidades técnicas en cloud computing, programación, DevOps y liderazgo técnico. Experiencia en las tecnologías más demandadas del mercado.' }
  ]
})

const skillCategories = [
  {
    icon: CloudIcon,
    name: 'Cloud Computing',
    description: 'AWS, Azure, GCP y arquitecturas cloud-native'
  },
  {
    icon: CodeBracketIcon,
    name: 'Programming',
    description: 'Lenguajes modernos y frameworks escalables'
  },
  {
    icon: CogIcon,
    name: 'DevOps',
    description: 'Automatización y entrega continua'
  },
  {
    icon: UserGroupIcon,
    name: 'Leadership',
    description: 'Gestión de equipos y liderazgo técnico'
  }
]

const cloudSkills = [
  {
    name: 'AWS',
    level: 'Expert',
    percentage: 95,
    description: 'EC2, Lambda, RDS, S3, CloudFormation, ECS/EKS'
  },
  {
    name: 'Azure',
    level: 'Advanced',
    percentage: 85,
    description: 'VM, Functions, SQL Database, Blob Storage, ARM'
  },
  {
    name: 'GCP',
    level: 'Advanced',
    percentage: 80,
    description: 'Compute Engine, Cloud Functions, BigQuery, GKE'
  },
  {
    name: 'Kubernetes',
    level: 'Expert',
    percentage: 90,
    description: 'Orquestación de contenedores, Helm, Istio'
  },
  {
    name: 'Docker',
    level: 'Expert',
    percentage: 95,
    description: 'Contenedores, Docker Compose, registries'
  },
  {
    name: 'Terraform',
    level: 'Advanced',
    percentage: 85,
    description: 'Infrastructure as Code, módulos, state management'
  }
]

const programmingSkills = [
  {
    name: 'Python',
    level: 'Expert',
    percentage: 95,
    description: 'Backend, APIs, data science, automation'
  },
  {
    name: 'JavaScript/Node.js',
    level: 'Expert',
    percentage: 90,
    description: 'Full-stack, APIs, microservices, React'
  },
  {
    name: 'Java',
    level: 'Advanced',
    percentage: 85,
    description: 'Spring Boot, microservices, enterprise apps'
  },
  {
    name: 'Go',
    level: 'Intermediate',
    percentage: 75,
    description: 'Microservices, cloud-native, performance'
  },
  {
    name: 'React',
    level: 'Advanced',
    percentage: 85,
    description: 'Frontend, hooks, state management'
  },
  {
    name: 'SQL',
    level: 'Expert',
    percentage: 90,
    description: 'PostgreSQL, MySQL, query optimization'
  }
]

const devopsSkills = [
  {
    name: 'CI/CD',
    level: 'Expert',
    percentage: 95,
    description: 'Jenkins, GitHub Actions, GitLab CI, pipelines'
  },
  {
    name: 'Monitoring',
    level: 'Advanced',
    percentage: 85,
    description: 'Prometheus, Grafana, ELK Stack, APM'
  },
  {
    name: 'Security',
    level: 'Advanced',
    percentage: 80,
    description: 'IAM, secrets management, compliance'
  },
  {
    name: 'Git',
    level: 'Expert',
    percentage: 95,
    description: 'Version control, branching strategies, GitOps'
  },
  {
    name: 'Linux',
    level: 'Advanced',
    percentage: 85,
    description: 'System administration, shell scripting'
  },
  {
    name: 'Networking',
    level: 'Intermediate',
    percentage: 75,
    description: 'VPC, load balancers, CDN, DNS'
  }
]

const softSkills = [
  {
    name: 'Technical Leadership',
    level: 'Expert',
    percentage: 95,
    description: 'Arquitectura de sistemas, toma de decisiones técnicas'
  },
  {
    name: 'Team Management',
    level: 'Advanced',
    percentage: 85,
    description: 'Gestión de equipos de desarrollo, mentoría'
  },
  {
    name: 'Communication',
    level: 'Expert',
    percentage: 90,
    description: 'Presentaciones técnicas, documentación, stakeholder management'
  },
  {
    name: 'Problem Solving',
    level: 'Expert',
    percentage: 95,
    description: 'Análisis de problemas complejos, diseño de soluciones'
  },
  {
    name: 'Project Management',
    level: 'Advanced',
    percentage: 80,
    description: 'Agile, Scrum, Kanban, risk management'
  },
  {
    name: 'Strategic Thinking',
    level: 'Advanced',
    percentage: 85,
    description: 'Planificación estratégica, roadmap tecnológico'
  }
]

const experiences = [
  {
    title: 'Senior Solutions Architect',
    company: 'TechCorp Solutions',
    period: '2022 - Presente',
    description: 'Lidero el diseño de arquitecturas escalables para clientes enterprise, especializándome en migraciones cloud y transformación digital.',
    technologies: ['AWS', 'Kubernetes', 'Python', 'Terraform', 'React']
  },
  {
    title: 'Lead Software Engineer',
    company: 'InnovateTech',
    period: '2020 - 2022',
    description: 'Dirigí el desarrollo de plataformas de e-commerce y fintech, implementando arquitecturas de microservicios y prácticas DevOps.',
    technologies: ['Node.js', 'Docker', 'Azure', 'MongoDB', 'Redis']
  },
  {
    title: 'DevOps Engineer',
    company: 'CloudFirst Systems',
    period: '2018 - 2020',
    description: 'Implementé pipelines de CI/CD y automatización de infraestructura, mejorando significativamente la velocidad de entrega.',
    technologies: ['Jenkins', 'Kubernetes', 'Terraform', 'Prometheus', 'Git']
  },
  {
    title: 'Full Stack Developer',
    company: 'Digital Solutions',
    period: '2016 - 2018',
    description: 'Desarrollé aplicaciones web y móviles, adquiriendo experiencia en múltiples tecnologías y metodologías ágiles.',
    technologies: ['JavaScript', 'React', 'Python', 'PostgreSQL', 'AWS']
  }
]
</script> 