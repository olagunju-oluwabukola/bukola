<script setup>

</script>

<template>

</template>

<style scoped>
@keyframes scroll-left {
  0% { transform: translateX(0); }
  100% { transform: translateX(-33.333%); }
}

@keyframes scroll-right {
  0% { transform: translateX(-33.333%); }
  100% { transform: translateX(0); }
}

@keyframes spin-slow {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.animate-spin-slow {
  animation: spin-slow 3s linear infinite;
}

.animate-scroll-left {
  animation: scroll-left 30s linear infinite;
}

.animate-scroll-right {
  animation: scroll-right 30s linear infinite;
}
</style>
