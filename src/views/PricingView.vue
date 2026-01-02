<script setup lang="ts">
import { ref } from 'vue'

const pricingPlans = ref([
  {
    type: 'Hourly',
    price: '60',
    features: [
      'One Psd Design',
      'One Html Template',
      'Responsive Design',
      'One Time Support',
      '24/7 Support',
    ],
  },
  {
    type: 'Monthly',
    price: '600',
    features: [
      'One Psd Design',
      'One Html Template',
      'Responsive Design',
      'Email Support',
      '24/7 Support',
    ],
  },
  {
    type: 'Full Time',
    price: '2000',
    features: [
      'One Psd Design',
      'One Html Template',
      'Responsive Design',
      'One Time Support',
      '24/7 Support',
    ],
  },
])
</script>

<template>
  <section class="max-w-6xl mx-auto text-center">
    <h2 class="text-3xl font-bold mb-16">Pricing Table</h2>
    <div class="grid md:grid-cols-3 gap-8">
      <div
        v-for="plan in pricingPlans"
        :key="plan.type"
        class="bg-[#2a2f35] pt-12 pb-8 px-6 rounded-sm relative group hover:bg-[#32383e] transition-all"
      >
        <div
          class="absolute top-6 left-0 bg-[#2ecc71] text-xs font-bold py-1 px-4 rounded-r-full shadow-lg"
        >
          Price
        </div>

        <h3 class="text-2xl font-bold mb-4">{{ plan.type }}</h3>
        <div class="text-[#2ecc71] mb-8">
          <span class="text-4xl font-black">${{ plan.price }}</span>
          <p class="text-gray-400 text-sm mt-1">{{ plan.type }} Plan</p>
        </div>

        <ul class="space-y-4 mb-10 text-gray-400 text-sm">
          <li v-for="feature in plan.features" :key="feature">{{ feature }}</li>
        </ul>

        <button
          class="btn btn-sm rounded-full bg-[#2ecc71] hover:bg-green-600 border-none px-8 text-white normal-case"
        >
          Hire Me
        </button>
      </div>
    </div>
  </section>
</template>
