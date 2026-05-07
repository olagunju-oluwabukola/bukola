<template>
  <div class="flex-1 px-6 py-12 overflow-y-auto">
    <div class="max-w-5xl mx-auto">
      <h1 class="text-4xl md:text-6xl font-bold mb-8 text-center">About Me</h1>

      <div class="grid md:grid-cols-2 gap-8 mb-12">
        <!-- Who I Am -->
        <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-8 border border-slate-700">
          <h2 class="text-2xl font-semibold mb-4">Who I Am</h2>
          <p class="text-slate-300 leading-relaxed mb-4">
            I'm Oluwabukola, a Frontend Engineer who specialises in building fast, accessible, and
            visually polished web applications. I bring a strong eye for detail and a systems-level
            mindset to every project I work on.
          </p>
          <p class="text-slate-300 leading-relaxed">
            I thrive in collaborative environments — working closely with designers, backend engineers,
            and product teams to ship experiences that are both technically sound and delightful to use.
          </p>
        </div>

        <!-- What I Do -->
        <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-8 border border-slate-700">
          <h2 class="text-2xl font-semibold mb-4">What I Do</h2>
          <ul class="space-y-3 text-slate-300">
            <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>Architect scalable component systems and front-end infrastructure that grow with your product</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>Build responsive, performant web applications with Vue.js, React, Nuxt, and Next.js</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>Translate Figma designs into pixel-perfect, accessible UI with clean, maintainable code</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>Optimise for Core Web Vitals, SEO, and long-term codebase health</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>Contribute meaningfully in code reviews, technical discussions, and cross-functional planning</span>
            </li>
          </ul>
        </div>
      </div>

      <!-- Skills -->
      <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-8 border border-slate-700">
        <h2 class="text-2xl font-semibold mb-2">Skills & Expertise</h2>
        <p class="text-slate-400 text-sm mb-6">Technologies I work with day-to-day</p>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
          <div
            v-for="skill in skills"
            :key="skill.name"
            class="bg-slate-700/50 rounded-lg p-3 text-center hover:bg-blue-500/20 hover:border-blue-500/50 border border-transparent transition-all duration-200 cursor-default"
          >
            <span class="text-lg mb-1 block">{{ skill.icon }}</span>
            <span class="text-sm font-medium">{{ skill.name }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const skills = [
  { name: 'JavaScript', icon: '⚡' },
  { name: 'Vue.js', icon: '💚' },
  { name: 'React', icon: '⚛️' },
  { name: 'Nuxt.js', icon: '🔷' },
  { name: 'Next.js', icon: '▲' },
  { name: 'Tailwind CSS', icon: '🎨' },
  { name: 'HTML & CSS', icon: '🧱' },
  { name: 'Firebase', icon: '🔥' },
  { name: 'Pinia', icon: '🍍' },
  { name: 'Redux', icon: '🔄' },
  { name: 'TanStack Query', icon: '🔃' },
  { name: 'Zustand', icon: '🐻' },
  { name: 'Zod', icon: '🛡️' },
]
</script>