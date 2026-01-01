<template>
  <div class="flex-1 px-6 py-12 overflow-y-auto">
    <div class="max-w-5xl mx-auto">
      <h1 class="text-4xl md:text-6xl font-bold mb-4 text-center">Education</h1>
      <p class="text-slate-300 text-center mb-12 max-w-2xl mx-auto">
        My academic background and certifications
      </p>

      <div class="mb-12">
        <h2 class="text-3xl font-semibold mb-6 flex items-center gap-3">
          <GraduationCap class="text-blue-400" />
          Academic Background
        </h2>
        <div class="space-y-6">
          <EducationItem
            v-for="(edu, index) in education"
            :key="index"
            :education="edu"
          />
        </div>
      </div>

      <div>
        <h2 class="text-3xl font-semibold mb-6 flex items-center gap-3">
          <Award class="text-blue-400" />
          Certifications
        </h2>
        <div class="grid md:grid-cols-2 gap-4">
          <CertificationItem
            v-for="(cert, index) in certifications"
            :key="index"
            :certification="cert"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { GraduationCap, Award } from 'lucide-vue-next'
import EducationItem from '../../components/edu-items.vue'
import CertificationItem from '../../components/certification.vue'

const education = [
  { degree: 'Bachelor of Education in Educational Management', institution: 'Obafemi Awolowo University', year: '2018 - 2024',  },
  { degree: 'Frontend Web Development Certificate', institution: 'She Code Africa Academy', year: '2020', description: 'An Intensive 12 weeks training program covering basics of web development and  modern JavaScript frameworks' },

]

const certifications = [
  'Responsive Web Design',
  'She code Africa Academy'
]
</script>