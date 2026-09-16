<script setup>
import { ref } from 'vue'
import emailjs from '@emailjs/browser'

const form = ref({ name: '', email: '', message: '' })
const isSending = ref(false)
const isSent = ref(false)
const error = ref('')

const sendEmail = () => {
  isSending.value = true
  error.value = ''

  const serviceID = 'service_3dikl86'
  const templateID = 'template_uc7fhe9'   
  const publicKey = 'rRyQeL5sPaKgXEbzI'
  const privateKey = 'J3aK87FWmQB4Q7T9TcMsE'  

  const templateParams = {
    name: form.value.name,
    email: form.value.email,
    project: 'Portfolio Contact',
    description: form.value.message,
  }

  emailjs.send(serviceID, templateID, templateParams, {
    publicKey: publicKey,
    privateKey: privateKey,       
  })
    .then((res) => {
      console.log('✅ EmailJS success:', res)
      isSending.value = false
      isSent.value = true
      form.value = { name: '', email: '', message: '' }
      setTimeout(() => (isSent.value = false), 3500)
    })
    .catch((err) => {
      console.error('❌ EmailJS error:', err)
      isSending.value = false
      error.value = err?.text || 'Failed to send. Please try again.'
    })
}
</script>

<template>
  <section id="contact" class="py-32 px-6 max-w-5xl mx-auto">
    <div class="text-center mb-20">
      <p class="text-[10px] uppercase tracking-[0.4em] text-secondary mb-4">Contact</p>
      <h2 class="text-3xl md:text-5xl font-display font-light">
        Let's build something <span class="italic text-secondary">worth remembering</span>.
      </h2>
      <p class="text-muted mt-6 max-w-lg mx-auto leading-relaxed">
        Whether it's a project, a role, or just a conversation — my inbox is open.
      </p>
    </div>

    <div class="grid md:grid-cols-5 gap-16">
      <!-- LEFT -->
      <div class="md:col-span-2 space-y-8">
        <div>
          <p class="text-[10px] uppercase tracking-[0.3em] text-muted mb-2">Email</p>
          <a href="mailto:fatima.ait.brik01@gmail.com"
             class="text-sm text-primary hover:text-secondary transition-colors">
            fatima.ait.brik01@gmail.com
          </a>
        </div>

        <div>
          <p class="text-[10px] uppercase tracking-[0.3em] text-muted mb-2">Phone</p>
          <a href="tel:+212625956668" class="text-sm text-primary hover:text-secondary transition-colors">
            +212 625 956 668
          </a>
        </div>

        <div>
          <p class="text-[10px] uppercase tracking-[0.3em] text-muted mb-2">Location</p>
          <p class="text-sm text-primary">Agadir, Morocco</p>
        </div>

        <div>
          <p class="text-[10px] uppercase tracking-[0.3em] text-muted mb-2">LinkedIn</p>
          <a href="https://www.linkedin.com/in/fatima-ait-brik-01027923b"
             target="_blank"
             class="inline-flex items-center gap-2 text-sm text-primary hover:text-secondary transition-colors">
            Connect with me
            <i class="ri-arrow-right-up-line"></i>
          </a>
        </div>

        <div class="pt-4">
          <a href="/Fatima_Ait_Brik_CV.pdf" download
             class="inline-flex items-center gap-2 border border-border text-primary px-6 py-3 rounded-full text-xs uppercase tracking-widest hover:border-secondary hover:text-secondary transition-all">
            Download CV
            <i class="ri-download-line"></i>
          </a>
        </div>
      </div>

      <!-- RIGHT -->
      <form @submit.prevent="sendEmail" class="md:col-span-3 space-y-6">
        <div class="grid md:grid-cols-2 gap-6">
          <div>
            <label class="block text-[10px] uppercase tracking-[0.3em] text-muted mb-2">Name</label>
            <input v-model="form.name" type="text" required placeholder="Your name"
              class="w-full bg-transparent border-b border-border focus:border-secondary text-primary placeholder:text-muted/50 py-2 outline-none transition-colors" />
          </div>

          <div>
            <label class="block text-[10px] uppercase tracking-[0.3em] text-muted mb-2">Email</label>
            <input v-model="form.email" type="email" required placeholder="you@email.com"
              class="w-full bg-transparent border-b border-border focus:border-secondary text-primary placeholder:text-muted/50 py-2 outline-none transition-colors" />
          </div>
        </div>

        <div>
          <label class="block text-[10px] uppercase tracking-[0.3em] text-muted mb-2">Message</label>
          <textarea v-model="form.message" required rows="5" placeholder="Tell me about your project..."
            class="w-full bg-transparent border-b border-border focus:border-secondary text-primary placeholder:text-muted/50 py-2 outline-none transition-colors resize-none"></textarea>
        </div>

        <button type="submit" :disabled="isSending"
          class="inline-flex items-center gap-2 bg-primary text-background px-8 py-3 rounded-full text-xs uppercase tracking-widest hover:opacity-90 transition-all disabled:opacity-50">
          <span v-if="isSending">Sending...</span>
          <span v-else-if="isSent">✓ Sent</span>
          <span v-else class="flex items-center gap-2">
            Send Message
            <i class="ri-arrow-right-line"></i>
          </span>
        </button>

        <p v-if="error" class="text-red-400 text-xs tracking-widest uppercase">{{ error }}</p>
      </form>
    </div>
  </section>
</template>