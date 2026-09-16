<template>
  <section id="about" class="py-32 px-6 max-w-6xl mx-auto">
    <div class="grid md:grid-cols-2 gap-20 items-center">
      <div class="flex justify-center">
        <div class="relative">
          <div class="absolute -inset-4 border rounded-2xl" style="border-color: color-mix(in srgb, var(--accent) 25%, transparent)"></div>
          <img src="/me.png" alt="Fatima"
               class="relative w-[260px] md:w-[340px] object-contain" />
        </div>
      </div>

      <div>
        <p class="text-[10px] uppercase tracking-[0.4em] text-secondary mb-6">About</p>

        <h2 class="text-3xl md:text-5xl font-display font-light leading-tight mb-8">
          Developer by craft.<br>
          <span class="italic text-secondary">Designer by instinct.</span>
        </h2>

        <div class="space-y-5 text-muted leading-relaxed">
          <p>
            I'm <span class="text-primary">Fatima Ait Brik</span>, a Full Stack Web Developer
            specializing in the MERN ecosystem. I build products that feel as good as they work.
          </p>

          <p>
            Over the past two years, I've moved from internship-scale projects to
            production-grade applications — from an educational CMS used in-house,
            to <span class="text-primary">DevApply</span>, a full SaaS job tracker
            with real-time analytics and email infrastructure.
          </p>

          <p>
            What drives me isn't just shipping features — it's the quiet detail: the
            weight of a button, the timing of a transition, the moment a user thinks
            <em class="not-italic text-secondary">"this just works."</em>
          </p>
        </div>

        <div class="mt-10 flex flex-wrap gap-3">
          <span class="text-xs border border-border rounded-full px-4 py-2 text-muted">Problem solver</span>
          <span class="text-xs border border-border rounded-full px-4 py-2 text-muted">Systems thinker</span>
          <span class="text-xs border border-border rounded-full px-4 py-2 text-muted">Detail obsessed</span>
        </div>
      </div>
    </div>
  </section>
</template>