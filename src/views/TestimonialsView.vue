<template>
  <section class="max-w-6xl mx-auto text-center">
    <h2 class="text-3xl font-bold mb-16">Customer Review</h2>
    <div class="grid md:grid-cols-3 gap-8">
      <div
        v-for="review in testimonials"
        :key="review.name"
        class="bg-[#2a2f35] p-10 rounded-sm relative"
      >
        <div class="avatar online absolute -top-10 left-1/2 -translate-x-1/2">
          <div class="w-20 rounded-full ring ring-[#2ecc71] ring-offset-base-100 ring-offset-2">
            <img :src="review.avatar" />
          </div>
        </div>
        <div class="mt-8">
          <p class="text-gray-400 italic text-sm leading-relaxed mb-6">
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce vitae risus nec dui
            venenatis."
          </p>
          <div class="rating rating-xs mb-2">
            <input type="radio" name="rating-2" class="mask mask-star-2 bg-orange-400" />
            <input type="radio" name="rating-2" class="mask mask-star-2 bg-orange-400" checked />
            <input type="radio" name="rating-2" class="mask mask-star-2 bg-orange-400" />
            <input type="radio" name="rating-2" class="mask mask-star-2 bg-orange-400" />
            <input type="radio" name="rating-2" class="mask mask-star-2 bg-orange-400" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const testimonials = ref([
  { name: 'User 1', avatar: 'https://i.pravatar.cc/150?u=1' },
  { name: 'User 2', avatar: 'https://i.pravatar.cc/150?u=2' },
  { name: 'User 3', avatar: 'https://i.pravatar.cc/150?u=3' },
])
</script>
