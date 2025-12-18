<template>
  <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-6 border border-slate-700">
    <h3 class="font-semibold mb-4">Social Media</h3>
    <div class="flex gap-4">
      <a href="https://x.com/Ofeyishayomi3" target="_blank"  class="w-12 h-12 bg-slate-700/50 rounded-full flex items-center justify-center hover:bg-slate-700 transition-colors">
        <Twitter :size="20" />
      </a>
      <a href="https://github.com/olagunju-oluwabukola" target="_blank"  class="w-12 h-12 bg-slate-700/50 rounded-full flex items-center justify-center hover:bg-slate-700 transition-colors">
        <Github :size="20" />
      </a>
      <a href="https://www.linkedin.com/in/oluwabukola-olagunju-434512229/" target="_blank" class="w-12 h-12 bg-slate-700/50 rounded-full flex items-center justify-center hover:bg-slate-700 transition-colors">
        <Linkedin :size="20" />
      </a>
    </div>
  </div>
</template>

<script setup>
import { Twitter, Github, Linkedin } from 'lucide-vue-next'
</script>