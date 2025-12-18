<template>
  <div class="overflow-hidden w-full">
    <div :style="rowStyle">
      <ProjectCard
        v-for="(project, index) in seamlessRow"
        :key="`${project.name}-${index}`"
        class="mr-6"
        :project="project"
      />
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'
import ProjectCard from './card.vue'

const props = defineProps({
  projects: {
    type: Array,
    required: true
  },
  direction: {
    type: String,
    default: 'left'
  },
  speed: {
    type: Number,
    default: 30
  }
})

const seamlessRow = computed(() => [
  ...props.projects,
  ...props.projects
])

const rowStyle = computed(() => ({
  display: 'flex',
  flexWrap: 'nowrap',
  width: 'max-content',
  animation: `${props.direction}-scroll ${props.speed}s linear infinite`
}))
</script>

<style scoped>
@keyframes left-scroll {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-50%);
  }
}

@keyframes right-scroll {
  from {
    transform: translateX(-50%);
  }
  to {
    transform: translateX(0);
  }
}
</style>
