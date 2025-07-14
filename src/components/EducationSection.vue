<template>
  <section id="education" class="container section-padding">
    <h2>Education</h2>
    <div 
      v-for="edu in education" 
      :key="edu.degree"
      class="education-entry"
    >
      <h3>{{ edu.degree }}</h3>
      <h4>{{ edu.institution }}</h4>
      <p class="date">{{ edu.period }}</p>
      <p v-if="edu.gpa">Cumulative GPA: {{ edu.gpa }}</p>
      <p v-if="edu.coursework">{{ edu.coursework }}</p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'EducationSection',
  setup() {
    const education = [
      {
        degree: 'Master of Business Administration (Information Technology)',
        institution: 'Kurukshetra University, Kurukshetra, Haryana',
        period: '2024 – 2026',
        gpa: null,
        coursework: null
      },
      {
        degree: 'Bachelor of Technology (Computer Science Engineering)',
        institution: 'J.C. Bose University of Science and Technology, YMCA, Faridabad, Haryana',
        period: '2019 - 2023',
        gpa: '7.78',
        coursework: 'Relevant Coursework: Data Analysis; Software Engineering; Operating Systems; Algorithms; Artificial Intelligence'
      }
    ]
    
    return {
      education
    }
  }
}
</script>

<style scoped>
/* Education section styles will be inherited from global CSS */
</style>
