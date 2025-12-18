<template>
  <div class="group relative flex-shrink-0 w-80 bg-slate-800/50 backdrop-blur-md rounded-2xl overflow-hidden border border-slate-700 hover:border-blue-500 transition-all">

    <div class="relative h-48 overflow-hidden">
      <img
        :src="project.image"
        :alt="project.name"
        class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-300"
      />

      <div class="absolute inset-0 bg-slate-900/90 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center gap-4 ">
        <a
          :href="project.github"
          target="_blank"
          rel="noopener noreferrer"
          class="px-4 py-2 bg-slate-700 hover:bg-slate-600 rounded-3xl flex items-center gap-2 transition-colors"
        >
          <Github :size="18" />
          GitHub
        </a>
        <a
          :href="project.demo"
          target="_blank"
          rel="noopener noreferrer"
          class="px-4 py-2 bg-blue-500 hover:bg-blue-600 rounded-3xl flex items-center gap-2 transition-colors"
        >
          <ExternalLink :size="18" />
          Live Demo
        </a>
      </div>
    </div>

    <div class="p-6">
      <h3 class="text-xl font-semibold mb-2 group-hover:text-blue-400 transition-colors">
        {{ project.name }}
      </h3>
      <p class="text-slate-400 text-sm">{{ project.tech }}</p>
    </div>
  </div>
</template>

<script setup>
import { Github, ExternalLink } from 'lucide-vue-next'

defineProps({
  project: {
    type: Object,
    required: true,
    default: () => ({
      name: '',
      tech: '',
      image: '',
      github: '',
      demo: ''
    })
  }
})
</script>