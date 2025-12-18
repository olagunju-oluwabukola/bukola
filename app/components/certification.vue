<template>
  <div class="bg-slate-800/50 backdrop-blur-md rounded-xl p-4 border border-slate-700 hover:border-slate-500 transition-all cursor-pointer hover:scale-105 flex items-center gap-3">
    <div class="w-10 h-10 bg-blue-500/20 rounded-full flex items-center justify-center flex-shrink-0">
      <Award :size="20" class="text-blue-400" />
    </div>
    <span class="text-slate-300">{{ certification }}</span>
  </div>
</template>

<script setup>
import { Award } from 'lucide-vue-next'

defineProps({
  certification: {
    type: String,
    required: true
  }
})
</script>