<template>
  <div class="flex-1 px-6 py-12 overflow-y-auto">
    <div class="max-w-5xl mx-auto">
      <h1 class="text-4xl md:text-6xl font-bold mb-4 text-center">Contact Me</h1>
      <p class="text-slate-300 text-center mb-12 max-w-2xl mx-auto">
        Reach out to me via my social media links below or send a message through the contact form.
      </p>

      <div class="grid md:grid-cols-2 gap-8 mb-12">
        <div class="space-y-6">
          <ContactInfoSection />
          <SocialMediaSection />
        </div>
        <ContactFormSection />
      </div>
    </div>
  </div>
</template>

<script setup>
import ContactInfoSection from '../../components/info.vue'
import SocialMediaSection from '../../components/media.vue'
import ContactFormSection from '../../components/form.vue'
</script>