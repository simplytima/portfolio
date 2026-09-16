<script setup>
defineProps({ darkMode: Boolean })
</script>

<template>
  <footer class="border-t border-border py-10 px-6">
    <div class="max-w-6xl mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
      <p class="text-xs text-muted tracking-widest uppercase">
        © {{ new Date().getFullYear() }} Fatima Ait Brik
      </p>

      <p class="text-xs text-muted italic">
        Designed & built from scratch.
      </p>

      <div class="flex gap-4">
        <a href="https://github.com/simplytima" target="_blank" class="text-muted hover:text-secondary transition-colors">
          <i class="ri-github-line text-lg"></i>
        </a>
        <a href="https://www.linkedin.com/in/fatima-ait-brik-01027923b" target="_blank" class="text-muted hover:text-secondary transition-colors">
          <i class="ri-linkedin-line text-lg"></i>
        </a>
      </div>
    </div>
  </footer>
</template>