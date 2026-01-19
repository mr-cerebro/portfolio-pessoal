<script setup lang="ts">
import { ref } from 'vue'

const projects = ref([
  {
    category: 'Desenvolvimento Web',
    title: 'Agr@Silfva - Comércio & Serviços',
    description: 'Empresa angolana vocacionada para oferecer soluções completas nos sectores da agricultura, pecuária e desinfestação.',
    image: 'https://galeria-de-fotos-css-column.vercel.app/assets/img/silvfa.ao.jpg',
    link: 'https://silvfa.ao/',
    tags: ['WordPress', 'Figma']
  },
  {
    category: 'Desenvolvimento Web',
    title: 'Mitana Training Consultants',
    description: 'O principal objetivo da Academia MITANA é fornecer programas de formação baseados em resultados de qualidade.',
    image: 'https://galeria-de-fotos-css-column.vercel.app/assets/img/mitanatraining-angola.jpg',
    link: 'https://mitanatraining-angola.com/',
    tags: ['WordPress', 'Figma']
  },
  {
    category: 'Mobile App',
    title: 'E-commerce App',
    description: 'Aplicação mobile para vendas online com integração de pagamentos locais.',
    image: 'https://galeria-de-fotos-css-column.vercel.app/assets/img/make-your-burger.jpg',
    link: 'hhttps://make-your-burger-lac.vercel.app/',
    tags: ['VueJS', 'JavaScript', 'Figma']
  },
])
</script>

<template>
  <section id="portfolio" class="max-w-6xl mx-auto text-center min-h-screen p-8 md:p-20 space-y-16">
    <div>
      <h2 class="text-4xl font-extrabold uppercase tracking-tighter">
        My <span class="text-[#fcb702]">Portfolio</span>
      </h2>
      <p class="text-gray-400 mt-4 max-w-2xl mx-auto">
        Conheça alguns dos meus trabalhos mais recentes, focados em soluções digitais e experiências interativas.
      </p>
    </div>

    <div class="grid md:grid-cols-3 gap-8">
      <div
        v-for="project in projects"
        :key="project.title"
        class="bg-[#1a1a1a] text-left overflow-hidden rounded-xl group border border-gray-800 hover:border-[#fcb702]/50 transition-all duration-500 shadow-2xl flex flex-col"
      >
        <div class="relative overflow-hidden aspect-video">
          <img
            :src="project.image"
            class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700"
          />
          <div class="absolute inset-0 bg-black/60 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300">
             <a
              :href="project.link"
              target="_blank"
              class="bg-[#fcb702] text-[#151515] px-6 py-2 rounded-full font-bold uppercase text-xs tracking-widest transform translate-y-4 group-hover:translate-y-0 transition-transform duration-300"
            >
              Ver Projeto <i class="fa fa-external-link ml-2"></i>
            </a>
          </div>
        </div>

        <div class="p-6 flex-grow flex flex-col justify-between">
          <div>
            <span class="text-[#fcb702] text-[10px] font-bold uppercase tracking-[2px]">
              {{ project.category }}
            </span>
            <h4 class="text-xl font-bold mt-2 mb-3 text-white group-hover:text-[#fcb702] transition-colors">
              {{ project.title }}
            </h4>
            <p class="text-gray-400 text-sm leading-relaxed mb-4">
              {{ project.description }}
            </p>
          </div>

          <div class="flex flex-wrap gap-2 pt-4 border-t border-gray-800">
            <span
              v-for="tag in project.tags"
              :key="tag"
              class="text-[10px] bg-gray-800 text-gray-300 px-2 py-1 rounded"
            >
              #{{ tag }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.group:hover {
  transform: translateY(-8px);
}
</style>
