<script setup>
const name = 'Fatima Ait Brik'
</script>

<template>
  <section class="min-h-screen flex items-center justify-center px-6 relative overflow-hidden pt-20">
    <div class="absolute inset-0 -z-10">
      <div class="absolute top-1/3 left-1/2 -translate-x-1/2 w-[600px] h-[600px] rounded-full blur-[120px]" style="background: color-mix(in srgb, var(--accent) 6%, transparent)"></div>
      <div class="absolute bottom-0 right-0 w-[400px] h-[400px] rounded-full blur-[100px]" style="background: color-mix(in srgb, var(--accent) 4%, transparent)"></div>
    </div>

    <div class="max-w-6xl mx-auto grid md:grid-cols-2 gap-16 items-center">
      <div class="text-center md:text-left order-2 md:order-1">
        <div class="inline-flex items-center gap-2 border border-border rounded-full px-4 py-1.5 mb-8">
          <span class="w-1.5 h-1.5 bg-emerald-400 rounded-full animate-pulse"></span>
          <span class="text-[10px] text-muted tracking-[0.3em] uppercase">Open to opportunities</span>
        </div>

        <h1 class="text-5xl md:text-7xl font-display font-light leading-[1.05] tracking-tight mb-6">
          I design & build
          <span class="block italic text-secondary">digital experiences</span>
          that matter.
        </h1>

        <p class="text-base md:text-lg text-muted font-light max-w-md mb-10 leading-relaxed">
          Full Stack Developer with a designer's eye. Turning complex problems into
          elegant, human-centered interfaces.
        </p>

        <div class="flex flex-col sm:flex-row gap-4 justify-center md:justify-start">
          <a href="#projects"
             class="inline-flex items-center justify-center gap-2 bg-primary text-background px-6 py-3 rounded-full font-medium text-sm tracking-wide hover:opacity-90 transition-all">
            Explore My Work
            <i class="ri-arrow-right-line"></i>
          </a>
          <a href="#contact"
             class="inline-flex items-center justify-center gap-2 border border-border px-6 py-3 rounded-full font-medium text-sm tracking-wide hover:border-secondary transition-all">
            Let's Talk
          </a>
        </div>
      </div>

      <div class="order-1 md:order-2 flex justify-center">
        <div class="relative">
          <div class="absolute inset-0 rounded-full blur-3xl" style="background: color-mix(in srgb, var(--accent) 12%, transparent)"></div>
          <img src="/me.png" alt="Fatima Ait Brik"
               class="relative w-[280px] md:w-[420px] object-contain grayscale hover:grayscale-0 transition-all duration-700" />
        </div>
      </div>
    </div>
  </section>
</template>