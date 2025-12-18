<template>
  <div class="flex-1 flex flex-col items-center justify-center px-6 relative overflow-hidden">
    <div class="absolute inset-0 flex items-center justify-center opacity-5">
      <h1 class="text-9xl font-bold">Oluwabukola</h1>
    </div>

    <div class="relative z-10 text-center mb-16">
      <h1 class="text-4xl md:text-6xl font-bold mb-8 font-mono">
        Hi, I am  {{ displayText }}<span class="animate-pulse">|</span>
      </h1>
      <p class="text-lg md:text-xl text-slate-300 max-w-2xl mx-auto">
        I am Oluwabukola, a passionate and excellence driven frontend developer with a eye for writing clean, pixel perfect, scalable and delivering solution driven codes.
      </p>
    </div>


  </div>
</template>

<script setup>
import { ref, watch, computed } from 'vue'


const texts = [
  "Oluwabukola.",
  "a Frontend Web Developer",
  "a Creative Problem Solver"
]

const displayText = ref('')
const currentTextIndex = ref(0)
const isDeleting = ref(false)
const charIndex = ref(0)


watch([charIndex, isDeleting, currentTextIndex], () => {
  const currentText = texts[currentTextIndex.value]
  const typingSpeed = isDeleting.value ? 50 : 100
  const pauseTime = isDeleting.value ? 500 : 2000

  if (!isDeleting.value && charIndex.value === currentText.length) {
    setTimeout(() => {
      isDeleting.value = true
    }, pauseTime)
    return
  }

  if (isDeleting.value && charIndex.value === 0) {
    isDeleting.value = false
    currentTextIndex.value = (currentTextIndex.value + 1) % texts.length
    return
  }

  setTimeout(() => {
    displayText.value = currentText.substring(0, charIndex.value)
    charIndex.value = isDeleting.value ? charIndex.value - 1 : charIndex.value + 1
  }, typingSpeed)
}, { immediate: true })
</script>