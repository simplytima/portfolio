<script setup>
const projects = [
  {
    id: 1,
    year: '2026',
    title: 'DevApply',
    role: 'Full Stack · SaaS',
    description: 'A complete job application tracker with real-time analytics, JWT authentication, and email-driven password recovery. Built end-to-end and deployed on Vercel.',
    tech: ['React', 'Node.js', 'MongoDB', 'JWT', 'TailwindCSS'],
    link: 'https://devapply-alpha.vercel.app',
    github: 'https://github.com/simplytima/devapply',
  },
  {
    id: 2,
    year: '2025',
    title: 'RessW4j',
    role: 'Educational CMS · Internship',
    description: 'A content management system for educational resources. Built responsive UIs and implemented CRUD, search, and pagination across the full stack.',
    tech: ['Laravel', 'Bootstrap', 'MySQL', 'JavaScript'],
    link: '#',
    github: '#',
  },
  {
    id: 3,
    year: '2024',
    title: 'ZenithOutlet',
    role: 'E-commerce Platform',
    description: 'A dual-sided marketplace giving merchants and customers a seamless, elegant shopping experience — from browsing to checkout.',
    tech: ['Vue.js', 'TailwindCSS', 'PHP', 'MySQL'],
    link: '#',
    github: '#',
  },

]
</script>

<template>
  <section id="projects" class="py-32 px-6 max-w-6xl mx-auto">
    <div class="text-center mb-16">
      <p class="text-[10px] uppercase tracking-[0.4em] text-secondary mb-4">Selected Work</p>
      <h2 class="text-3xl md:text-5xl font-display font-light">
        Things I've <span class="italic text-secondary">shipped</span>.
      </h2>
    </div>

    <div class="space-y-4">
      <a v-for="project in projects" :key="project.id"
         :href="project.link" target="_blank"
         class="group block bg-surface border border-border rounded-2xl p-6 md:p-8
                hover:border-secondary transition-all duration-300">
        <div class="grid md:grid-cols-12 gap-6 items-start">
          <div class="md:col-span-2">
            <p class="text-xs text-muted tracking-widest">{{ project.year }}</p>
          </div>

          <div class="md:col-span-7">
            <h3 class="text-2xl md:text-3xl font-display font-light mb-2 group-hover:text-secondary transition-colors">
              {{ project.title }}
            </h3>
            <p class="text-xs uppercase tracking-widest text-muted mb-4">{{ project.role }}</p>
            <p class="text-muted leading-relaxed">{{ project.description }}</p>

            <div class="flex flex-wrap gap-2 mt-6">
              <span v-for="tech in project.tech" :key="tech"
                    class="text-[10px] uppercase tracking-widest border border-border rounded-full px-3 py-1 text-muted">
                {{ tech }}
              </span>
            </div>
          </div>

          <div class="md:col-span-3 md:text-right">
            <span class="inline-flex items-center gap-2 text-sm text-secondary">
              View project
              <i class="ri-arrow-right-up-line group-hover:translate-x-1 group-hover:-translate-y-1 transition-transform"></i>
            </span>
          </div>
        </div>
      </a>
    </div>
  </section>
</template>