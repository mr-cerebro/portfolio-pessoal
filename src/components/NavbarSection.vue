<script setup lang="ts">
import { ref } from 'vue'

const Links = ref({
  home: 'Home',
  about: 'About me',
  service: 'Services',
  skills: 'Skilss',
  experiences: 'Experiences',
  portfolio: 'Portfolio',
  contact: 'Contact me',
})

const scrollToSection = (e: Event, id: string) => {
  e.preventDefault()
  const element = document.getElementById(id)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<template>
<nav class="flex justify-between items-center px-12 py-6 mx-w-7xl mx-auto --font-open">
    <div class="text-xl font-bol">Paulo Pessoa</div>
    <ul class="hidden md:flex space-x-6 text-sm font-medium text-gray-300">
      <li>
        <a href="#home" @click="scrollToSection($event, 'home')" class="hover:text-[#fcb702]">{{
          Links.home
        }}</a>
      </li>
      <li>
        <a href="#about" @click="scrollToSection($event, 'about')" class="hover:text-[#fcb702]">{{
          Links.about
        }}</a>
      </li>
      <li>
        <a href="#service" @click="scrollToSection($event, 'service')" class="hover:text-[#fcb702]">{{
          Links.service
        }}</a>
      </li>
      <li>
        <a href="#skills" @click="scrollToSection($event, 'skills')" class="hover:text-[#fcb702]">{{
          Links.skills
        }}</a>
      </li>
      <li>
        <a
          href="#experiences"
          @click="scrollToSection($event, 'experiences')"
          class="hover:text-[#fcb702]"
          >{{ Links.experiences }}</a
        >
      </li>
      <li>
        <a
          href="#portfolio"
          @click="scrollToSection($event, 'portfolio')"
          class="hover:text-[#fcb702]"
          >{{ Links.portfolio }}</a
        >
      </li>
      <li>
        <a
          href="#contact"
          @click="scrollToSection($event, 'contact')"
          class="hover:text-[#fcb702]"
          >{{ Links.contact }}</a
        >
      </li>
    </ul>
  </nav>
</template>

