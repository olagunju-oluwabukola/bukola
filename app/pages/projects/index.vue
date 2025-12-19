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
import img1 from "@/assets/images/bookie.png"
import img2 from "@/assets/images/fabel craft.png"
import img3 from "@/assets/images/funiro.png"
import img4 from "@/assets/images/nuxt store.png"
import img5 from "@/assets/images/artsy.png"
import img6 from "@/assets/images/haven.png"
const projects = [
  { name: "Bookie", tech: "Nuxt.js + Firebase + Tailwind", image: img1, github: "https://github.com/olagunju-oluwabukola/Bookie", demo:"https://bookie-gold-two.vercel.app/" },
  { name: "Fable Craft", tech: "Next.js + Grok AI + Tailwind", image: img2,  github: "https://github.com/olagunju-oluwabukola/story-forge", demo:"https://story-forge-eta.vercel.app/" },
  { name: "Furniro", tech: "Nuxt.js + Tailwind ", image:img3, github: "https://github.com/olagunju-oluwabukola/Furniro", demo:"https://furniro-ten-taupe.vercel.app/" },
  { name: "Nuxt Store", tech: "Nuxt + Tailwind", image: img4, github: "https://github.com/olagunju-oluwabukola/NuxtStore", demo:"https://nuxt-store-tawny.vercel.app/" },
  { name: "Artsy", tech: "Vue + Tailwind", image: img5, github: "https://github.com/olagunju-oluwabukola/Artsy", demo:"https://artsy-rhq2.vercel.app/"},
  { name: "Harven", tech: "React + Tailwind ", image: img6, github: "https://github.com/olagunju-oluwabukola/Harven-Estates", demo:"https://github.com/olagunju-oluwabukola/Harven-Estates"},
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
