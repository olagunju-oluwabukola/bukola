<template>
  <div class="fixed bottom-8 left-1/2 transform -translate-x-1/2 z-50">
    <div class="bg-slate-800/80 backdrop-blur-lg rounded-full px-4 py-3 shadow-2xl border border-slate-700">
      <div class="flex items-center gap-2">
        <button
          v-for="item in navItems"
          :key="item.path"
          @click="$emit('navigate', item.path)"
          :class="[
            'p-3 rounded-full transition-all duration-300',
            currentPage === item.path
              ? 'bg-white text-slate-900 scale-110'
              : 'text-slate-300 hover:bg-slate-700 hover:text-white'
          ]"
          :title="item.label"
        >
          <component :is="item.icon" :size="24" />
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  Home, User, Mail, Code, Wrench, GraduationCap
} from 'lucide-vue-next'

defineProps({
  currentPage: {
    type: String,
    default: '/'
  }
})

defineEmits(['navigate'])

const navItems = [
  { icon: Home, label: 'Home', path: '/' },
  { icon: User, label: 'About', path: '/about' },
    { icon: Code, label: 'Projects', path: '/projects' },
  { icon: Wrench, label: 'Tools', path: '/tools' },
  { icon: Mail, label: 'Contact', path: '/contact' },
  { icon: GraduationCap, label: 'Education', path: '/education' },
]
</script>