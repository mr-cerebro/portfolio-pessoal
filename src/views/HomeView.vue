<script setup lang="ts">
import { ref } from 'vue'

const Links = ref({
  home: 'Home',
  about: 'About me',
  skills: 'Skilss',
  experiences: 'Experiences',
  portfolio: 'Portfolio',
  contact: 'Contact me',
})
</script>

<template>
  <nav class="flex justify-between items-center px-12 py-6 mx-w-7xl mx-auto --font-open">
    <div class="text-xl font-bol">Paulo Pessoa</div>
    <ul class="hidden md:flex space-x-6 text-sm font-medium text-gray-300">
      <li>
        <a href="#" class="hover:text-[#fcb702]">{{ Links.home }}</a>
      </li>
      <li>
        <a href="#" class="hover:text-[#fcb702]">{{ Links.about }}</a>
      </li>
      <li>
        <a href="#" class="hover:text-[#fcb702]">{{ Links.skills }}</a>
      </li>
      <li>
        <a href="#" class="hover:text-[#fcb702]">{{ Links.experiences }}</a>
      </li>
      <li>
        <a href="#" class="hover:text-[#fcb702]">{{ Links.portfolio }}</a>
      </li>
      <li>
        <a href="#" class="hover:text-[#fcb702]">{{ Links.contact }}</a>
      </li>
    </ul>
  </nav>

  <section class="max-w-7xl mx-auto px-12 py-20 grid md:grid-cols-2 gap-8 items-center --font-open">
    <div class="flex justify-center">
      <div class="relative w-80 rounded-2xl overflow-hidden border-b-8 border-[#fbc702]">
        <img src="/img/profile.png" alt="Profile" class="object-cover w-full h-full" />
      </div>
    </div>
    <div class="space-y-4">
      <span class="bg-[#fcb702] text-sm font-bold px-4 py-1 rounded uppercase text-[#151515]"
        >Hello There!</span
      >
      <h1 class="text-6xl font-extrabold">I'M Paulo Pessoa</h1>
      <p class="text-xl text-gray-400">Front-end Developer / UI Designer</p>

      <div class="pt-6 space-y-2 text-gray-400 text-sm">
        <p><i class="fa fa-map-marker w-6"></i>Luanda, Angola</p>
        <p><i class="fa fa-whatsapp w-6"></i>+244 932 954 022</p>
        <p><i class="fa fa-envelope-o w-6"></i>mrcerebro8@gmail.com</p>
      </div>

      <div class="flex space-x-4 pt-4">
        <a
          href="#"
          class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-[#0866ff] transition"
          ><i class="fa fa-behance"></i
        ></a>
        <a
          href="#"
          class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-[#0866ff] transition"
          ><i class="fa fa-facebook"></i
        ></a>
        <a
          href="#"
          class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-[#0b0f10] transition"
          ><i class="fa fa-github"></i
        ></a>
        <a
          href="#"
          class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-gradient-to-tr from-[#f9ce34] via-[#ee2a7b] to-[#6228d7] transition"
          ><i class="fa fa-instagram"></i
        ></a>
        <a
          href="#"
          class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-[#136bc5] transition"
          ><i class="fa fa-linkedin"></i
        ></a>
      </div>
    </div>
  </section>
</template>
