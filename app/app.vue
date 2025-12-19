<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-700 via-slate-800 to-slate-900 text-white flex flex-col">

    <LoadingScreen v-if="isLoading" />

    <template v-else>
      <component :is="currentPageComponent" />


      <BottomNavigation
        :current-page="currentPage"
        @navigate="currentPage = $event"
      />
    </template>

    <AnimationStyles />
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from 'vue'
import LoadingScreen from './components/loader.vue'
import BottomNavigation from './components/nav.vue'
import AnimationStyles from './components/animation.vue'
import HomePage from './pages/index.vue'
import AboutPage from './pages/About/index.vue'
import ContactPage from './pages/contact/index.vue'
import ProjectsPage from './pages/projects/index.vue'
import ToolsPage from './pages/Tools/index.vue'
import EducationPage from './pages/Education/index.vue'

useHead({
    title: 'Oluwabukola | Frontend Developer',
  link: [
    {
      rel: 'icon',
      type: 'image/jpg',
      href: '/favicon.jpg'
    }
  ]
})


const isLoading = ref(true)
const currentPage = ref('/')
onMounted(() => {
  setTimeout(() => {
    isLoading.value = false
  }, 3000)
})

const currentPageComponent = computed(() => {
  const pages = {
    '/': HomePage,
    '/about': AboutPage,
    '/contact': ContactPage,
    '/projects': ProjectsPage,
    '/tools': ToolsPage,
    '/education': EducationPage,
  }
  return pages[currentPage.value] || HomePage
})
</script>