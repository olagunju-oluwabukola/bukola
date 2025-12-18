<template>
  <div class="flex-1 px-6 py-12 overflow-y-auto">
    <div class="max-w-7xl mx-auto">
      <h1 class="text-4xl md:text-6xl font-bold mb-4 text-center">Projects</h1>
      <p class="text-slate-300 text-center mb-12 max-w-2xl mx-auto">
        Explore my development projects and technical implementations
      </p>

      <div class="overflow-hidden mb-8">
        <div
          class="row left"
          :style="{ animationPlayState: pauseRow[0] ? 'paused' : 'running' }"
        >
          <ProjectCard
            v-for="(project, i) in row1"
            :key="`r1-${i}`"
            :project="project"
            @mouseenter="pause(0)"
            @mouseleave="resume(0)"
          />
        </div>
      </div>


      <div class="overflow-hidden mb-8">
        <div
          class="row right"
          :style="{ animationPlayState: pauseRow[1] ? 'paused' : 'running' }"
        >
          <ProjectCard
            v-for="(project, i) in row2"
            :key="`r2-${i}`"
            :project="project"
            @mouseenter="pause(1)"
            @mouseleave="resume(1)"
          />
        </div>
      </div>

      <div class="overflow-hidden">
        <div
          class="row left slow"
          :style="{ animationPlayState: pauseRow[2] ? 'paused' : 'running' }"
        >
          <ProjectCard
            v-for="(project, i) in row3"
            :key="`r3-${i}`"
            :project="project"
            @mouseenter="pause(2)"
            @mouseleave="resume(2)"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ProjectCard from "@/components/card.vue"

const projects = [
  { name: "Task Manager", tech: "Vue + Firebase", image: "https://images.unsplash.com/photo-1557821552-17105176677", github: "https://github.com/olagunju-oluwabukola/story-forge", demo:"https://story-forge-eta.vercel.app/" },
  { name: "Weather App", tech: "React + API", image: "https://images.unsplash.com/photo-1592210454359-9043f067919b", github: "", demo:"" },
  { name: "Blog CMS", tech: "WordPress", image: "https://images.unsplash.com/photo-1499750310107-5fef28a66643", github: "", demo:"" },
  { name: "Portfolio", tech: "Nuxt", image: "https://images.unsplash.com/photo-1460925895917-afdab827c52f", github: "", demo:"" },
  { name: "Chat App", tech: "Vue + Socket", image: "https://images.unsplash.com/photo-1611746872915-64382b5c76da", github: "", demo:""},
  { name: "E-learning", tech: "React + Node", image: "https://images.unsplash.com/photo-1501504905252-473c47e087f8", github: "", demo:""},
]


const row1 = [...projects, ...projects]
const row2 = [...projects, ...projects]
const row3 = [...projects, ...projects]


const pauseRow = ref([false, false, false])

const pause = (index) => {
  pauseRow.value[index] = true
}

const resume = (index) => {
  pauseRow.value[index] = false
}
</script>

<style scoped>
.row {
  display: flex;
  gap: 1.5rem;
  width: max-content;
  animation: scroll-left 25s linear infinite;
}

.row.right {
  animation: scroll-right 30s linear infinite;
}

.row.slow {
  animation-duration: 40s;
}

@keyframes scroll-left {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

@keyframes scroll-right {
  0% {
    transform: translateX(-50%);
  }
  100% {
    transform: translateX(0);
  }
}
</style>
