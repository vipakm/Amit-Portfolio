<template>
  <header id="hero">
    <div class="particles" ref="particles"></div>
    <div class="container">
      <div class="hero-content">
        <h1>AMIT KUMAR</h1>
        <h2 class="typewriter" ref="typewriter">Software Engineering</h2>
        <p class="hero-description">
          Passionate about building robust and scalable web applications with cutting-edge technologies.
        </p>
        <div class="hero-buttons">
          <a href="#contact" class="btn-primary" @click="scrollToSection('contact')">Get In Touch</a>
          <a href="#projects" class="btn-secondary" @click="scrollToSection('projects')">View Projects</a>
        </div>
        <div class="social-links">
          <a href="https://www.linkedin.com/in/mr-amitkumar/" target="_blank" aria-label="LinkedIn">
            <i class="fab fa-linkedin"></i>
          </a>
          <a href="https://github.com/vipakm" target="_blank" aria-label="GitHub">
            <i class="fab fa-github"></i>
          </a>
          <a href="mailto:mramit4848@gmail.com" aria-label="Email">
            <i class="fas fa-envelope"></i>
          </a>
          <a href="tel:+918178796716" aria-label="Phone">
            <i class="fas fa-phone"></i>
          </a>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import { ref, onMounted } from 'vue'

export default {
  name: 'HeroSection',
  setup() {
    const particles = ref(null)
    const typewriter = ref(null)
    
    const scrollToSection = (sectionId) => {
      const element = document.getElementById(sectionId)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
      }
    }
    
    const createParticle = (container) => {
      const particle = document.createElement('div')
      particle.className = 'particle'
      particle.style.cssText = `
        position: absolute;
        width: 2px;
        height: 2px;
        background: rgba(255, 255, 255, 0.1);
        border-radius: 50%;
        pointer-events: none;
        left: ${Math.random() * 100}%;
        top: ${Math.random() * 100}%;
        animation: float ${5 + Math.random() * 10}s infinite linear;
      `
      
      container.appendChild(particle)
      
      setTimeout(() => {
        if (particle.parentNode) {
          particle.parentNode.removeChild(particle)
        }
      }, 15000)
    }
    
    const initParticles = () => {
      if (particles.value) {
        for (let i = 0; i < 50; i++) {
          createParticle(particles.value)
        }
      }
    }
    
    const initTypewriter = () => {
      if (!typewriter.value) return
      
      const text = typewriter.value.textContent
      typewriter.value.textContent = ''
      
      let i = 0
      const typeWriter = () => {
        if (i < text.length) {
          typewriter.value.textContent += text.charAt(i)
          i++
          setTimeout(typeWriter, 100)
        }
      }
      
      setTimeout(typeWriter, 1000)
    }
    
    onMounted(() => {
      initParticles()
      initTypewriter()
    })
    
    return {
      particles,
      typewriter,
      scrollToSection
    }
  }
}
</script>

<style scoped>
/* Hero section styles will be inherited from global CSS */
</style>
