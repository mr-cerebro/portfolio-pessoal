<template>
  <nav
    :class="[
      'fixed top-0 left-0 w-full z-100 transition-all duration-300 px-6 md:px-12 flex justify-between items-center',
      isScrolled || isMenuOpen
        ? 'bg-[#151515] py-4 shadow-xl border-b border-gray-800'
        : 'bg-transparent py-8',
    ]"
  >
    <div class="text-xl font-bold text-white">Paulo Pessoa</div>

    <button @click="isMenuOpen = !isMenuOpen" class="block md:hidden text-white p-2 z-110">
      <div class="w-6 h-5 flex flex-col justify-between items-end">
        <span
          :class="[
            'h-0.5 bg-[#fcb702] transition-all',
            isMenuOpen ? 'w-6 translate-y-2 -rotate-45' : 'w-6',
          ]"
        ></span>
        <span
          :class="['h-0.5 bg-[#fcb702] transition-all', isMenuOpen ? 'opacity-0' : 'w-4']"
        ></span>
        <span
          :class="[
            'h-0.5 bg-[#fcb702] transition-all',
            isMenuOpen ? 'w-6 -translate-y-2 rotate-45' : 'w-5',
          ]"
        ></span>
      </div>
    </button>

    <ul class="hidden md:flex space-x-8 text-sm font-medium">
      <li v-for="(label, key) in Links" :key="key">
        <a
          :href="'#' + key"
          @click.prevent="scrollToSection(key as string)"
          :class="[
            'transition-colors duration-300 tracking-wider',
            activeSection === key ? 'text-[#fcb702]' : 'text-gray-400 hover:text-white',
          ]"
        >
          {{ label }}
        </a>
      </li>
    </ul>

    <div
      :class="[
        'fixed inset-0 bg-[#151515] flex flex-col items-center justify-center space-y-8 transition-all duration-500 md:hidden',
        isMenuOpen ? 'translate-x-0 opacity-100' : 'translate-x-full opacity-0',
      ]"
    >
      <a
        v-for="(label, key) in Links"
        :key="key"
        @click.prevent="scrollToSection(key as string)"
        :class="[
          'text-2xl font-bold transition-colors',
          activeSection === key ? 'text-[#fcb702]' : 'text-gray-400',
        ]"
      >
        {{ label }}
      </a>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMenuOpen = ref(false)
const activeSection = ref('home')

const Links = {
  home: 'Home',
  about: 'About me',
  skills: 'Skills',
  portfolio: 'Portfolio',
  contact: 'Contact me',
}

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const scrollToSection = (id: string) => {
  isMenuOpen.value = false
  const element = document.getElementById(id)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)

  // --- LÓGICA DO ACTIVE LINK ---
  const observerOptions = {
    root: null,
    rootMargin: '-40% 0px -40% 0px', // Detecta quando a seção está no centro
    threshold: 0,
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        activeSection.value = entry.target.id
      }
    })
  }, observerOptions)

  // Observa todas as seções que têm ID e estão no seu App.vue
  document.querySelectorAll('section[id]').forEach((section) => {
    observer.observe(section)
  })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
