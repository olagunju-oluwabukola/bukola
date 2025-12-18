<template>
  <div class="flex-1 px-6 py-12 overflow-y-auto">
    <div class="max-w-5xl mx-auto">
      <h1 class="text-4xl md:text-6xl font-bold mb-8 text-center">About Me</h1>

      <div class="grid md:grid-cols-2 gap-8 mb-12">
        <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-8 border border-slate-700">
          <h2 class="text-2xl font-semibold mb-4">Who I Am</h2>
          <p class="text-slate-300 leading-relaxed mb-4">
            I'm Oluwabukola, a passionate Frontend Web Developer with expertise in modern web technologies.
            I'm dedicated to crafting responsive, high performance, pixel perfect web appliactions, and
continuous learning.
          </p>
          <p class="text-slate-300 leading-relaxed">
          I'm adept at collaborating with cross-functional teams to transform design mockups
into functional and scalable code.
          </p>
        </div>

        <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-8 border border-slate-700">
          <h2 class="text-2xl font-semibold mb-4">What I Do</h2>
          <ul class="space-y-3 text-slate-300">
            <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>Build responsive and modern web applications</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>Contribute to code and participate in code reviews</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>Create seamless user experiences with Vue.js and React</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>Optimize website performance and SEO</span>
            </li>
             <li class="flex items-start gap-3">
              <span class="text-blue-400 mt-1">▹</span>
              <span>figma to code conversion</span>
            </li>
          </ul>
        </div>
      </div>

      <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-8 border border-slate-700">
        <h2 class="text-2xl font-semibold mb-6">Skills & Expertise</h2>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
          <div v-for="skill in skills" :key="skill" class="bg-slate-700/50 rounded-lg p-3 text-center hover:bg-slate-700 transition-colors">
            {{ skill }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const skills = ['JavaScript', 'Vue.js', 'React', 'Nuxt.js', 'Next.js', 'Tailwind CSS', 'HTML/CSS', 'Firebase', 'pinia']
</script>