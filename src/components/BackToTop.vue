<template>
  <button 
    id="backToTop" 
    class="back-to-top" 
    :class="{ show: isVisible }"
    @click="scrollToTop"
    aria-label="Back to top"
  >
    <i class="fas fa-chevron-up"></i>
  </button>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue'

export default {
  name: 'BackToTop',
  setup() {
    const isVisible = ref(false)
    
    const scrollToTop = () => {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }
    
    const handleScroll = () => {
      isVisible.value = window.pageYOffset > 100
    }
    
    onMounted(() => {
      window.addEventListener('scroll', handleScroll)
    })
    
    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll)
    })
    
    return {
      isVisible,
      scrollToTop
    }
  }
}
</script>

<style scoped>
/* Back to top styles will be inherited from global CSS */
</style>
