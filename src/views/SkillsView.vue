<template>
  <div class="min-h-screen p-8 md:p-20 font-sans">
    <section class="max-w-6xl mx-auto grid grid-cols-2 md:grid-cols-4 gap-y-12 gap-x-4 mb-32">
      <div v-for="skill in skills" :key="skill.name" class="flex flex-col items-center gap-4">
        <div
          class="radial-progress text-[#2ecc71] border-4 border-[#2a2f35] bg-[#1e2329]"
          :style="{ '--value': skill.value, '--size': '8rem', '--thickness': '4px' }"
          role="progressbar"
        >
          <span class="text-white text-xl font-bold">{{ skill.value }}%</span>
        </div>
        <span class="text-gray-400 font-medium tracking-wide">{{ skill.name }}</span>
      </div>
    </section>

    <section class="max-w-6xl mx-auto mb-32 text-center">
      <h2 class="text-3xl font-bold mb-16">My Education & Experience</h2>
      <div class="grid md:grid-cols-2 gap-6 text-left">
        <div
          v-for="item in timeline"
          :key="item.title"
          class="bg-[#2a2f35] p-8 rounded-sm hover:shadow-xl transition-all border-l-0 hover:border-l-4 border-[#2ecc71]"
        >
          <h3 class="text-lg font-bold mb-1">{{ item.title }}</h3>
          <p class="text-sm mb-4">
            <span class="text-[#2ecc71] font-bold">{{ item.date }}</span>
            <span class="text-gray-400"> - {{ item.subtitle }}</span>
          </p>
          <p class="text-gray-400 text-sm leading-relaxed">{{ item.desc }}</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

// Dados para as habilidades (Skills)
const skills = ref([
  { name: 'HTML', value: 75 },
  { name: 'CSS3', value: 70 },
  { name: 'Bootstrap', value: 85 },
  { name: 'Jquery', value: 60 },
  { name: 'Javascript', value: 65 },
  { name: 'Photoshop', value: 88 },
  { name: 'Marketing', value: 70 },
  { name: 'Branding', value: 80 },
])

// Dados para Educação e Experiência
const timeline = ref([
  {
    title: 'The Lawrenceville School',
    date: '2005',
    subtitle: 'Secondary School Certificate',
    desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae accusantium consectetur.',
  },
  {
    title: 'AleSmith Brewing Company',
    date: '2012',
    subtitle: 'IT Executive',
    desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae accusantium consectetur.',
  },
  {
    title: 'Adams State College',
    date: '2007',
    subtitle: 'Higher Secondary Certificate',
    desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae accusantium consectetur.',
  },
  {
    title: 'Applied Micro Circuits Corporation',
    date: '2013',
    subtitle: 'Web Developer',
    desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae accusantium consectetur.',
  },
  {
    title: 'Florida Hospital College',
    date: '2012',
    subtitle: 'Bachelor Degree',
    desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae accusantium consectetur.',
  },
  {
    title: 'Upwork/Fiverr',
    date: '2014 to Present',
    subtitle: 'Web Developer',
    desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae accusantium consectetur.',
  },
])
</script>
