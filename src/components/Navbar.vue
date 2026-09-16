<script setup>
import { ref } from 'vue'

const props = defineProps({ darkMode: Boolean })
const emit = defineEmits(['toggleDarkMode'])
const menuOpen = ref(false)

const sections = ['home', 'about', 'skills', 'projects', 'contact']
</script>

<template>
  <nav class="fixed top-0 w-full z-50 bg-background/70 backdrop-blur-lg border-b border-border">
    <div class="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
      <a href="#" class="flex items-center gap-3 group">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 60 60" class="w-8 h-8 text-primary group-hover:text-secondary transition-colors">
          <rect x="1" y="1" width="58" height="58" rx="14" stroke="currentColor" stroke-width="1.5" fill="none"/>
          <text x="30" y="41" text-anchor="middle"
                font-family="Playfair Display, serif"
                font-size="28" font-style="italic"
                fill="currentColor">F</text>
        </svg>
        <span class="hidden md:block font-display text-xs tracking-[0.3em] uppercase text-muted group-hover:text-primary transition-colors">
          Fatima Ait Brik
        </span>
      </a>

      <div class="hidden md:flex items-center gap-10">
        <a v-for="s in sections" :key="s" :href="'#' + s"
           class="text-xs uppercase tracking-widest text-muted hover:text-primary transition-colors">
          {{ s }}
        </a>
        <button @click="emit('toggleDarkMode')" class="text-lg text-muted hover:text-secondary transition-colors">
          <i :class="darkMode ? 'ri-sun-line' : 'ri-moon-line'"></i>
        </button>
      </div>

      <div class="flex items-center gap-4 md:hidden">
        <button @click="emit('toggleDarkMode')" class="text-lg">
          <i :class="darkMode ? 'ri-sun-line' : 'ri-moon-line'"></i>
        </button>
        <button @click="menuOpen = !menuOpen" class="text-2xl">
          <i :class="menuOpen ? 'ri-close-line' : 'ri-menu-line'"></i>
        </button>
      </div>
    </div>

    <div v-if="menuOpen" class="md:hidden border-t border-border bg-background/95 backdrop-blur-lg">
      <div class="flex flex-col px-6 py-4 gap-4">
        <a v-for="s in sections" :key="s" :href="'#' + s"
           class="text-xs uppercase tracking-widest text-muted hover:text-primary"
           @click="menuOpen = false">
          {{ s }}
        </a>
      </div>
    </div>
  </nav>
</template>