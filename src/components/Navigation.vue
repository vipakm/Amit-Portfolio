<template>
  <nav id="navbar" :class="{ 'scrolled': isScrolled }">
    <div class="container">
      <ul>
        <li><a href="#about" :class="{ active: activeSection === 'about' }" @click="scrollToSection('about')">About</a></li>
        <li><a href="#skills" :class="{ active: activeSection === 'skills' }" @click="scrollToSection('skills')">Skills</a></li>
        <li><a href="#experience" :class="{ active: activeSection === 'experience' }" @click="scrollToSection('experience')">Experience</a></li>
        <li><a href="#projects" :class="{ active: activeSection === 'projects' }" @click="scrollToSection('projects')">Projects</a></li>
        <li><a href="#education" :class="{ active: activeSection === 'education' }" @click="scrollToSection('education')">Education</a></li>
        <li><a href="#contact" :class="{ active: activeSection === 'contact' }" @click="scrollToSection('contact')">Contact</a></li>
      </ul>
    </div>
  </nav>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue'

export default {
  name: 'Navigation',
  setup() {
    const isScrolled = ref(false)
    const activeSection = ref('')
    
    const scrollToSection = (sectionId) => {
      const element = document.getElementById(sectionId)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
      }
    }
    
    const handleScroll = () => {
      isScrolled.value = window.pageYOffset > 100
      
      // Update active section
      const sections = document.querySelectorAll('section[id]')
      let current = ''
      
      sections.forEach(section => {
        const sectionTop = section.offsetTop
        if (window.pageYOffset >= sectionTop - 200) {
          current = section.getAttribute('id')
        }
      })
      
      activeSection.value = current
    }
    
    onMounted(() => {
      window.addEventListener('scroll', handleScroll)
      handleScroll()
    })
    
    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll)
    })
    
    return {
      isScrolled,
      activeSection,
      scrollToSection
    }
  }
}
</script>

<style scoped>
/* Navigation styles will be inherited from global CSS */
</style>
