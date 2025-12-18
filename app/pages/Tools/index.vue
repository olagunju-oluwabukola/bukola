<template>
  <div class="flex-1 px-6 py-12 overflow-y-auto">
    <div class="max-w-5xl mx-auto">
      <h1 class="text-4xl md:text-6xl font-bold mb-4 text-center">Tools</h1>
      <p class="text-slate-300 text-center mb-12 max-w-2xl mx-auto">
        Technologies and languages I use
      </p>

      <div class="grid md:grid-cols-2 gap-8">
        <ToolCategory
          v-for="(category, index) in toolCategories"
          :key="index"
          :category="category"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import ToolCategory from '../../components/category.vue'

const toolCategories = [
  { category: 'Languages', tools: [ 'JavaScript', 'Golang (learning)'] },
  { category: 'Frameworks & Libraries', tools: ['Vue.js', 'React', 'Nuxt.js', 'Next.js', 'Tailwind CSS', 'Bootstrap'] },
  { category: 'Tools & Platforms', tools: ['Git', 'GitHub', 'Firebase', 'VS Code', 'Figma', 'Postman'] },
  { category: 'Other Skills', tools: ['REST APIs', 'Responsive Design', 'SEO', 'Content Management System'] }
]
</script>