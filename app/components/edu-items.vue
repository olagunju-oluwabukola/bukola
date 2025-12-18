<template>
  <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-6 border border-slate-700 hover:border-slate-500 transition-all">
    <div class="flex items-start justify-between mb-3">
      <h3 class="text-xl font-semibold text-blue-400">{{ education.degree }}</h3>
      <span class="flex items-center gap-2 text-slate-400 text-sm">
        <Calendar :size="16" />
        {{ education.year }}
      </span>
    </div>
    <p class="text-lg text-slate-300 mb-2">{{ education.institution }}</p>
    <p class="text-slate-400">{{ education.description }}</p>
  </div>
</template>

<script setup>
import { Calendar } from 'lucide-vue-next'

defineProps({
  education: {
    type: Object,
    required: true,
    default: () => ({
      degree: '',
      institution: '',
      year: '',
      description: ''
    })
  }
})
</script>