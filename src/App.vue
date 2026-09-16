<script setup>
import { ref, onMounted } from 'vue'
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

const darkMode = ref(false)

const applyTheme = (isDark) => {
  const root = document.documentElement
  root.classList.toggle('dark', isDark)
  root.classList.toggle('light', !isDark)
  localStorage.setItem('theme', isDark ? 'dark' : 'light')
}

const toggleDarkMode = () => {
  darkMode.value = !darkMode.value
  applyTheme(darkMode.value)
}

onMounted(() => {
  const saved = localStorage.getItem('theme')
  darkMode.value = saved === 'dark' 
})
</script>

<template>
  <div class="min-h-screen">
    <Navbar :darkMode="darkMode" @toggleDarkMode="toggleDarkMode" />
    <main>
      <Hero />
      <About />
      <Skills />
      <Projects />
      <Contact />
    </main>
    <Footer :darkMode="darkMode" />
  </div>
</template>