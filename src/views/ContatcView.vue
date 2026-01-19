<template>
  <div class="bg-[#1e2329] text-white min-h-screen p-8 md:p-20 font-sans">
    <section class="max-w-4xl mx-auto text-center mb-32">
      <h2 class="text-3xl font-bold mb-12">Get In Touch</h2>

      <form @submit.prevent="handleSubmit" class="space-y-4">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <input
            v-model="formData.name"
            type="text"
            placeholder="Name"
            class="input input-bordered w-full bg-[#2a2f35] border-none focus:ring-1 focus:ring-[#2ecc71] text-sm"
          />
          <input
            v-model="formData.email"
            type="email"
            placeholder="Email"
            class="input input-bordered w-full bg-[#2a2f35] border-none focus:ring-1 focus:ring-[#2ecc71] text-sm"
          />
          <input
            v-model="formData.subject"
            type="text"
            placeholder="Subject"
            class="input input-bordered w-full bg-[#2a2f35] border-none focus:ring-1 focus:ring-[#2ecc71] text-sm"
          />
        </div>

        <textarea
          v-model="formData.message"
          placeholder="Your Message"
          class="textarea textarea-bordered w-full bg-[#2a2f35] border-none focus:ring-1 focus:ring-[#2ecc71] h-40 text-sm"
        ></textarea>

        <div class="flex justify-center pt-4">
          <button
            type="submit"
            class="btn rounded-full bg-[#2ecc71] hover:bg-green-600 border-none px-12 text-white normal-case shadow-lg"
          >
            Send Message
          </button>
        </div>
      </form>
    </section>

    <footer class="max-w-6xl mx-auto text-center border-t border-gray-800 pt-12 pb-8">
      <h3 class="text-lg font-bold mb-6">Paulo Pessoa</h3>
      <div class="flex flex-wrap justify-center gap-x-6 gap-y-2 text-xs text-gray-400 mb-12">
        <a
          v-for="link in socialLinks"
          :key="link"
          href="#"
          class="hover:text-[#fcb702] transition-colors"
        >
          {{ link }}
        </a>
      </div>

      <div class="flex justify-end">
        <button
          @click="scrollToTop"
          class="w-10 h-10 bg-[#2a2f35] rounded-sm flex items-center justify-center hover:bg-[#2ecc71] transition-all"
        >
          <i class="fa fa-chevron-up text-xs"></i>
        </button>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const formData = ref({
  name: '',
  email: '',
  subject: '',
  message: '',
})

const socialLinks = ['Behance', 'Facebook', 'GitHub', 'Instagram', 'LinkedIn']

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

const handleSubmit = () => {
  console.log('Formulário enviado:', formData.value)
  alert('Mensagem enviada com sucesso!')
}
</script>
