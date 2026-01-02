<script setup lang="ts">
import NavbarSection from './components/NavbarSection.vue'
import AboutView from './views/AboutView.vue'
import ContatcView from './views/ContatcView.vue'
import HomeView from './views/HomeView.vue'
import PortfolioView from './views/PortfolioView.vue'
import ServiceView from './views/ServiceView.vue'
import SkillsView from './views/SkillsView.vue'

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

    <main class="pt-24">
      <section id="home">
        <HomeView />
      </section>

      <section id="about">
        <AboutView />
      </section>

      <section id="service">
        <ServiceView />
      </section>

      <section id="skills">
        <SkillsView />
      </section>

      <section id="portfolio">
        <PortfolioView />
      </section>

      <section id="contact">
        <ContatcView />
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
  scroll-margin-top: 5px;
}
</style>
