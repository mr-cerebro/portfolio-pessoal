<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'

const isScrolled = ref(false)
const activeSection = ref('home')

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)

  const observerOptions = {
    root: null,
    rootMargin: '-50% 0px -50% 0px',
    threshold: 0,
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        activeSection.value = entry.target.id
      }
    })
  }, observerOptions)

  document.querySelectorAll('section[id]').forEach((section) => {
    observer.observe(section)
  })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <nav
    :class="[
      'fixed top-0 left-0 w-full z-50 transition-all duration-300 px-12 items-center flex justify-between',
      isScrolled ? 'bg-[#151515]/90 backdrop-blur-md py-4' : 'bg-transparent py-8',
    ]"
  >
    <div class="text-xl font-bol">Paulo Pessoa</div>
    <ul class="hidden md:flex space-x-6 text-sm font-medium">
      <li
        v-for="(label, key) in {
          home: 'Home',
          about: 'About me',
          service: 'Services',
          skills: 'Skills',
          portfolio: 'Portfolio',
          contact: 'Contact',
        }"
        :key="key"
      >
        <a
          :href="'#' + key"
          :class="[
            'transition-colors duration-300',
            activeSection === key ? 'text-[#fcb702]' : 'text-gray-300 hover:text-white',
          ]"
        >
          {{ label }}
        </a>
      </li>
    </ul>
  </nav>
</template>
