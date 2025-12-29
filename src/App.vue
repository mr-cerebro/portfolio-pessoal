<script setup lang="ts">
import NavbarSection from './components/NavbarSection.vue'
import AboutView from './views/AboutView.vue'
import HomeView from './views/HomeView.vue'

const scrollToSection = (e: Event, id: string) => {
  e.preventDefault()
  const element = document.getElementById(id)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<template>
  <div>
    <NavbarSection @navigate="scrollToSection" />

    <main>
      <section id="home">
        <HomeView />
      </section>

      <section id="about">
        <AboutView />
      </section>
    </main>
  </div>
</template>

<style scoped>
  html {
  scroll-behavior: smooth;
}

section {
  min-height: 100vh;
}
</style>
