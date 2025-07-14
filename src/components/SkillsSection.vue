<template>
  <section id="skills" class="container section-padding">
    <h2>Key Skills</h2>
    <div class="skills-grid">
      <div 
        v-for="category in skillCategories" 
        :key="category.title"
        class="skill-category card"
      >
        <h3>
          <i :class="category.icon"></i>
          {{ category.title }}
        </h3>
        <div 
          v-for="skill in category.skills" 
          :key="skill.name"
          class="skill-item"
        >
          <span>{{ skill.name }}</span>
          <div class="skill-bar">
            <div 
              class="skill-progress" 
              :data-width="skill.level"
              :style="{ width: isVisible ? skill.level : '0%' }"
            ></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { ref, onMounted } from 'vue'

export default {
  name: 'SkillsSection',
  setup() {
    const isVisible = ref(false)
    
    const skillCategories = [
      {
        title: 'Programming Languages',
        icon: 'fas fa-code',
        skills: [
          { name: 'C#', level: '90%' },
          { name: 'JavaScript', level: '85%' },
          { name: 'PySpark', level: '75%' },
          { name: 'C/C++', level: '60%' }
        ]
      },
      {
        title: 'Frontend',
        icon: 'fas fa-paint-brush',
        skills: [
          { name: 'HTML/CSS', level: '95%' },
          { name: 'Bootstrap', level: '85%' },
          { name: 'Svelte Kit JS', level: '70%' }
        ]
      },
      {
        title: 'Backend',
        icon: 'fas fa-server',
        skills: [
          { name: 'ASP.NET Core', level: '90%' },
          { name: 'Web API', level: '88%' },
          { name: 'ASP.NET WebForm', level: '80%' }
        ]
      },
      {
        title: 'Database',
        icon: 'fas fa-database',
        skills: [
          { name: 'Microsoft SQL Server', level: '85%' },
          { name: 'MySQL', level: '80%' }
        ]
      },
      {
        title: 'Cloud & Data Engineering',
        icon: 'fas fa-cloud',
        skills: [
          { name: 'Azure Data Factory', level: '75%' },
          { name: 'Databricks', level: '70%' }
        ]
      },
      {
        title: 'Version Control & Tools',
        icon: 'fab fa-git-alt',
        skills: [
          { name: 'Git/GitHub', level: '85%' },
          { name: 'Azure DevOps', level: '75%' }
        ]
      }
    ]
    
    const observeSkills = () => {
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            isVisible.value = true
          }
        })
      }, { threshold: 0.3 })
      
      const skillsSection = document.getElementById('skills')
      if (skillsSection) {
        observer.observe(skillsSection)
      }
    }
    
    onMounted(() => {
      observeSkills()
    })
    
    return {
      skillCategories,
      isVisible
    }
  }
}
</script>

<style scoped>
/* Skills section styles will be inherited from global CSS */
</style>
