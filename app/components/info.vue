<template>
  <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-6 border border-slate-700">
    <div class="flex items-center gap-4 mb-6">
      <div class="w-12 h-12 bg-blue-500/20 rounded-full flex items-center justify-center">
        <Phone class="text-blue-400" :size="24" />
      </div>
      <div>
        <h3 class="font-semibold">Phone</h3>
        <p class="text-slate-400">(+234)8038581725</p>
      </div>
    </div>

    <div class="flex items-center gap-4 mb-6">
      <div class="w-12 h-12 bg-blue-500/20 rounded-full flex items-center justify-center">
        <Mail class="text-blue-400" :size="24" />
      </div>
      <div>
        <h3 class="font-semibold">Email</h3>
        <p class="text-slate-400">olagunjuoluwabukola2018@gmail.com</p>
      </div>
    </div>

    <div class="flex items-center gap-4">
      <div class="w-12 h-12 bg-blue-500/20 rounded-full flex items-center justify-center">
        <MapPin class="text-blue-400" :size="24" />
      </div>
      <div>
        <h3 class="font-semibold">Location</h3>
        <p class="text-slate-400">Lagos, Nigeria</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { Phone, Mail, MapPin } from 'lucide-vue-next'
</script>