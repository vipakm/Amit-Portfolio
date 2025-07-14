<template>
  <section id="contact" class="container section-padding">
    <h2>Get In Touch</h2>
    <p class="contact-intro">
      I'm currently open to new opportunities and exciting projects. Let's connect and discuss how we can work together!
    </p>
    
    <div class="contact-content">
      <div class="contact-info-cards">
        <div class="contact-card card">
          <div class="contact-icon">
            <i class="fas fa-envelope"></i>
          </div>
          <h3>Email</h3>
          <p>mramit4848@gmail.com</p>
          <a href="mailto:mramit4848@gmail.com" class="btn-primary">Send Email</a>
        </div>
        <div class="contact-card card">
          <div class="contact-icon">
            <i class="fas fa-phone"></i>
          </div>
          <h3>Phone</h3>
          <p>+91 8178796716</p>
          <a href="tel:+918178796716" class="btn-primary">Call Now</a>
        </div>
        <div class="contact-card card">
          <div class="contact-icon">
            <i class="fab fa-linkedin"></i>
          </div>
          <h3>LinkedIn</h3>
          <p>Connect with me</p>
          <a href="https://www.linkedin.com/in/mr-amitkumar/" target="_blank" class="btn-primary">Connect</a>
        </div>
      </div>

      <div class="contact-form-container">
        <form class="contact-form card" @submit.prevent="submitForm">
          <h3>Send a Message</h3>
          <div class="form-group">
            <input 
              v-model="form.name" 
              type="text" 
              placeholder="Your Name" 
              required
            >
          </div>
          <div class="form-group">
            <input 
              v-model="form.email" 
              type="email" 
              placeholder="Your Email" 
              required
            >
          </div>
          <div class="form-group">
            <input 
              v-model="form.subject" 
              type="text" 
              placeholder="Subject" 
              required
            >
          </div>
          <div class="form-group">
            <textarea 
              v-model="form.message" 
              placeholder="Your Message" 
              rows="5" 
              required
            ></textarea>
          </div>
          <button type="submit" class="btn-primary">
            <i class="fas fa-paper-plane"></i>
            Send Message
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'ContactSection',
  setup() {
    const form = ref({
      name: '',
      email: '',
      subject: '',
      message: ''
    })
    
    const submitForm = () => {
      const { name, email, subject, message } = form.value
      
      if (!name || !email || !subject || !message) {
        alert('Please fill in all fields.')
        return
      }
      
      const mailtoLink = `mailto:mramit4848@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(`Name: ${name}\nEmail: ${email}\n\nMessage:\n${message}`)}`
      
      window.location.href = mailtoLink
      
      // Reset form
      form.value = {
        name: '',
        email: '',
        subject: '',
        message: ''
      }
      
      alert('Thank you for your message! Your email client should open now.')
    }
    
    return {
      form,
      submitForm
    }
  }
}
</script>

<style scoped>
/* Contact section styles will be inherited from global CSS */
</style>
