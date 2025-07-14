<template>
  <footer>
    <div class="container">
      <div class="footer-content">
        <div class="footer-section">
          <h3>Amit Kumar</h3>
          <p>Software Developer passionate about building innovative web solutions.</p>
        </div>
        <div class="footer-section">
          <h3>Quick Links</h3>
          <ul>
            <li><a href="#about" @click="scrollToSection('about')">About</a></li>
            <li><a href="#skills" @click="scrollToSection('skills')">Skills</a></li>
            <li><a href="#experience" @click="scrollToSection('experience')">Experience</a></li>
            <li><a href="#projects" @click="scrollToSection('projects')">Projects</a></li>
          </ul>
        </div>
        <div class="footer-section">
          <h3>Connect</h3>
          <div class="footer-social">
            <a href="https://www.linkedin.com/in/mr-amitkumar/" target="_blank">
              <i class="fab fa-linkedin"></i>
            </a>
            <a href="https://github.com/vipakm" target="_blank">
              <i class="fab fa-github"></i>
            </a>
            <a href="mailto:mramit4848@gmail.com">
              <i class="fas fa-envelope"></i>
            </a>
          </div>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2025 Amit Kumar. All rights reserved. | Built with ❤️ and lots of ☕</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterSection',
  setup() {
    const scrollToSection = (sectionId) => {
      const element = document.getElementById(sectionId)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
      }
    }
    
    return {
      scrollToSection
    }
  }
}
</script>

<style scoped>
/* Footer styles will be inherited from global CSS */
</style>
