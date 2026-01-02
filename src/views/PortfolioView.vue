<script setup lang="ts">
import { ref } from 'vue'

const blogPosts = ref([
  {
    date: '08 July, 2020',
    title: 'Team You Want To Work',
    image: 'https://picsum.photos/400/250?random=10',
  },
  {
    date: '09 July, 2020',
    title: 'Lights Winged Seasons Fish',
    image: 'https://picsum.photos/400/250?random=11',
  },
  {
    date: '10 July, 2020',
    title: 'Winged Moved Stars',
    image: 'https://picsum.photos/400/250?random=12',
  },
])
</script>

<template>
  <section class="max-w-6xl mx-auto text-center min-h-screen p-8 md:p-20 space-y-32">
    <h2 class="text-3xl font-bold mb-16">Latest News</h2>
    <div class="grid md:grid-cols-3 gap-8">
      <div
        v-for="post in blogPosts"
        :key="post.title"
        class="bg-[#2a2f35] text-left overflow-hidden rounded-sm group"
      >
        <div class="relative">
          <img
            :src="post.image"
            class="w-full h-48 object-cover group-hover:scale-105 transition-transform duration-500"
          />
          <div
            class="absolute top-4 left-4 bg-[#2ecc71] text-[10px] font-bold py-1 px-3 rounded-sm"
          >
            {{ post.date }}
          </div>
        </div>
        <div class="p-6">
          <h4 class="text-lg font-bold mb-3 group-hover:text-[#2ecc71] transition-colors">
            {{ post.title }}
          </h4>
          <p class="text-gray-400 text-xs leading-relaxed mb-4">
            Lorem ipsum dolor sit amet, consectetur adipiscing elitsed nonummy nibh euismod.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Transição suave para os cards */
.group:hover {
  transform: translateY(-5px);
}
</style>
