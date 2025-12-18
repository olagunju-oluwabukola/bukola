<template>
  <div class="min-h-screen flex items-center justify-center">
    <div class="text-center">
      <div class="w-32 h-32 mx-auto mb-8 relative">
      <div
    v-if="show"
    class="fixed inset-0   flex items-center justify-center z-[9999] transition-opacity duration-700"
    :class="{ 'opacity-0 pointer-events-none': !visible }"
  >
  <div class="justify-center items-center gap-10">
        <img
      :src="logo"
      alt="Church Logo"
      class="w-28 h-28 rounded-full object-cover animate-spin-slow"
    />
    <div>

    </div>

  </div>

  </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import logo from "../assets/images/IMG_20240812_162829.jpg"

const show = ref(true)
const visible = ref(true)

onMounted(() => {
  setTimeout(() => {
    visible.value = false
  }, 2000)

  setTimeout(() => {
    show.value = false
  }, 2700)
})
</script>

<style scoped>
@keyframes spin-slow {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
.animate-spin-slow {
  animation: spin-slow 5s linear infinite;
}
</style>