<template>
  <div id="loading-screen" v-if="isVisible">
    <div class="loader">
      <div class="loader-text">AMIT KUMAR</div>
      <div class="loader-bar"></div>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'

export default {
  name: 'LoadingScreen',
  setup() {
    const isVisible = ref(true)
    
    onMounted(() => {
      setTimeout(() => {
        isVisible.value = false
      }, 1000)
    })
    
    return {
      isVisible
    }
  }
}
</script>

<style scoped>
/* Loading screen styles will be inherited from global CSS */
</style>
