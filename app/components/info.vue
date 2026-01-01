<template>
  <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-6 border border-slate-700">
    <div class="flex items-center gap-4 mb-6">
      <div class="w-10 h-10 bg-blue-500/20 rounded-full flex items-center justify-center shrink-0">
        <Phone class="text-blue-400" :size="20" />
      </div>
      <div class="min-w-0">
        <h3 class="font-semibold">Phone</h3>
        <p class="text-slate-400 break-all">(+234)8038581725</p>
      </div>
    </div>

    <div class="flex items-center gap-4 mb-6">
      <div class="w-10 h-10 bg-blue-500/20 rounded-full flex items-center justify-center shrink-0">
        <Mail class="text-blue-400" :size="20" />
      </div>
      <div class="min-w-0">
        <h3 class="font-semibold">Email</h3>
        <p class="text-slate-400 break-all">
          olagunjuoluwabukola2018@gmail.com
        </p>
      </div>
    </div>

    <div class="flex items-center gap-4">
      <div class="w-10 h-10 bg-blue-500/20 rounded-full flex items-center justify-center shrink-0">
        <MapPin class="text-blue-400" :size="20" />
      </div>
      <div class="min-w-0">
        <h3 class="font-semibold">Location</h3>
        <p class="text-slate-400">Lagos, Nigeria</p>
      </div>
    </div>
  </div>
</template>


<script setup>
import { Phone, Mail, MapPin } from 'lucide-vue-next'
</script>