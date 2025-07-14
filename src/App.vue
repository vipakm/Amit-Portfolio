<template>
  <div id="app">
    <!-- Loading Screen -->
    <LoadingScreen v-if="isLoading" />
    
    <!-- Hero Section -->
    <HeroSection />
    
    <!-- Navigation -->
    <Navigation />
    
    <!-- Main Content -->
    <main>
      <AboutSection />
      <SkillsSection />
      <ExperienceSection />
      <ProjectsSection />
      <EducationSection />
      <ContactSection />
    </main>
    
    <!-- Back to Top Button -->
    <BackToTop />
    
    <!-- Footer -->
    <FooterSection />
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
import LoadingScreen from './components/LoadingScreen.vue'
import HeroSection from './components/HeroSection.vue'
import Navigation from './components/Navigation.vue'
import AboutSection from './components/AboutSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import EducationSection from './components/EducationSection.vue'
import ContactSection from './components/ContactSection.vue'
import BackToTop from './components/BackToTop.vue'
import FooterSection from './components/FooterSection.vue'

export default {
  name: 'App',
  components: {
    LoadingScreen,
    HeroSection,
    Navigation,
    AboutSection,
    SkillsSection,
    ExperienceSection,
    ProjectsSection,
    EducationSection,
    ContactSection,
    BackToTop,
    FooterSection
  },
  setup() {
    const isLoading = ref(true)
    
    onMounted(() => {
      setTimeout(() => {
        isLoading.value = false
      }, 1000)
    })
    
    return {
      isLoading
    }
  }
}
</script>

<style>
/* Global styles will be imported in main.js */
</style>
