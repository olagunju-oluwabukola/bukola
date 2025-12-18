<template>
  <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-8 border border-slate-700">
    <h2 class="text-2xl font-semibold mb-6 text-blue-400">{{ category.category }}</h2>
    <div class="grid grid-cols-2 gap-3">
      <div
        v-for="tool in category.tools"
        :key="tool"
        class="bg-slate-700/50 rounded-lg p-3 text-center hover:bg-slate-700 transition-colors cursor-pointer hover:scale-105"
      >
        {{ tool }}
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  category: {
    type: Object,
    required: true,
    default: () => ({
      category: '',
      tools: []
    })
  }
})
</script>