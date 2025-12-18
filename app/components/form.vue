<template>
  <div class="bg-slate-800/50 backdrop-blur-md rounded-2xl p-6 border border-slate-700">
    <form @submit.prevent="handleSubmit" class="space-y-4">
      <div>
        <label class="block text-sm font-semibold mb-2">Name :</label>
        <input
          v-model="formData.name"
          type="text"
          placeholder="Enter Name"
          class="w-full bg-slate-900/50 border border-slate-700 rounded-lg px-4 py-3 focus:outline-none focus:border-blue-500 transition-colors"
          required
        />
      </div>

      <div>
        <label class="block text-sm font-semibold mb-2">Email Address</label>
        <input
          v-model="formData.email"
          type="email"
          placeholder="Enter email address"
          class="w-full bg-slate-900/50 border border-slate-700 rounded-lg px-4 py-3 focus:outline-none focus:border-blue-500 transition-colors"
          required
        />
      </div>

      <div>
        <label class="block text-sm font-semibold mb-2">Subject</label>
        <input
          v-model="formData.subject"
          type="text"
          placeholder="Enter message subject"
          class="w-full bg-slate-900/50 border border-slate-700 rounded-lg px-4 py-3 focus:outline-none focus:border-blue-500 transition-colors"
          required
        />
      </div>

      <div>
        <label class="block text-sm font-semibold mb-2">Message</label>
        <textarea
          v-model="formData.message"
          placeholder="Enter Message"
          rows="5"
          class="w-full bg-slate-900/50 border border-slate-700 rounded-lg px-4 py-3 focus:outline-none focus:border-blue-500 transition-colors resize-none"
          required
        />
      </div>

      <button
        type="submit"
        class="w-full bg-blue-500 hover:bg-blue-600 text-white font-semibold py-3 rounded-lg transition-colors flex items-center justify-center gap-2"
      >
        <Send :size="20" />
        Send Message
      </button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Send } from 'lucide-vue-next'

const formData = ref({
  name: '',
  email: '',
  subject: '',
  message: '',
})

const handleSubmit = () => {
  const recipient = 'olagunjuoluwabukola2018@gmail.com'
  const subject = encodeURIComponent(formData.value.subject)
  const body = encodeURIComponent(
    `Name: ${formData.value.name}\nEmail: ${formData.value.email}\n\n${formData.value.message}`
  )
  const mailtoLink = `mailto:${recipient}?subject=${subject}&body=${body}`
  window.location.href = mailtoLink
  formData.value = { name: '', email: '', subject: '', message: '' }
}
</script>
