<script setup>
const skills = [
  { name: 'JavaScript',  icon: 'devicon-javascript-plain',  color: '#F7DF1E' },
  { name: 'TypeScript',  icon: 'devicon-typescript-plain',  color: '#3178C6' },
  { name: 'React',       icon: 'devicon-react-original',    color: '#61DAFB' },
  { name: 'Vue.js',      icon: 'devicon-vuejs-plain',       color: '#4FC08D' },
  { name: 'Node.js',     icon: 'devicon-nodejs-plain',      color: '#339933' },
  { name: 'Express',     icon: 'devicon-express-original',  color: 'currentColor' }, // adaptive
  { name: 'PHP',         icon: 'devicon-php-plain',         color: '#777BB4' },
  { name: 'Laravel',     icon: 'devicon-laravel-plain',     color: '#FF2D20' },
  { name: 'MySQL',       icon: 'devicon-mysql-plain',       color: '#00758F' },
  { name: 'MongoDB',     icon: 'devicon-mongodb-plain',     color: '#47A248' },
  { name: 'TailwindCSS', icon: 'devicon-tailwindcss-plain', color: '#06B6D4' },
  { name: 'Git',         icon: 'devicon-git-plain',         color: '#F05032' },
]
</script>

<template>
  <section id="skills" class="py-32 px-6 max-w-6xl mx-auto">
    <div class="text-center mb-16">
      <p class="text-[10px] uppercase tracking-[0.4em] text-secondary mb-4">Toolkit</p>
      <h2 class="text-3xl md:text-5xl font-display font-light">
        The <span class="italic text-secondary">tools</span> behind the work.
      </h2>
    </div>

    <div class="grid grid-cols-3 md:grid-cols-4 lg:grid-cols-6 gap-4">
      <div v-for="skill in skills" :key="skill.name"
           class="group aspect-square flex flex-col items-center justify-center
                  bg-surface border border-border rounded-2xl
                  hover:border-secondary transition-all duration-300 hover:-translate-y-1">
        <i
          :class="[skill.icon, 'text-3xl md:text-4xl mb-3 transition-transform group-hover:scale-110']"
          :style="{ color: skill.color === 'currentColor' ? 'var(--text)' : skill.color }"
        ></i>
        <p class="text-[10px] md:text-xs uppercase tracking-widest text-muted group-hover:text-primary transition-colors">
          {{ skill.name }}
        </p>
      </div>
    </div>
  </section>
</template>