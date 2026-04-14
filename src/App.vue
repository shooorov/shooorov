<script setup>
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import ContactSection from './components/ContactSection.vue'
import SectionNavigator from './components/SectionNavigator.vue'
import { onMounted } from 'vue'

onMounted(() => {
  // Simple scroll behavior
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
      const target = document.querySelector(this.getAttribute('href'));
      if (target) {
        e.preventDefault();
        target.scrollIntoView({
          behavior: 'smooth'
        });
      }
    });
  });
})
</script>

<template>
  <SectionNavigator />
  <main class="portfolio">
    <HeroSection />
    <AboutSection />
    <ExperienceSection />
    <ProjectsSection />
    <ContactSection />
  </main>
</template>

<style>
.portfolio {
  padding-bottom: 2rem;
  margin-left: 200px; /* Space for the floating navigator */
  transition: margin 0.3s ease;
}

@media (max-width: 1200px) {
  .portfolio {
    margin-left: 150px;
  }
}

@media (max-width: 768px) {
  .portfolio {
    margin-left: 0;
    padding: 0 1rem;
  }
}
</style>
