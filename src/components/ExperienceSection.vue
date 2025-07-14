<template>
  <section id="experience" class="container section-padding">
    <h2>Work Experience</h2>
    <div class="timeline">
      <div 
        v-for="(job, index) in experiences" 
        :key="index"
        class="timeline-item"
      >
        <div class="timeline-marker"></div>
        <div class="timeline-content card">
          <h3>{{ job.position }}</h3>
          <h4>{{ job.company }}</h4>
          <p class="date">{{ job.period }}</p>
          <ul>
            <li v-for="(responsibility, idx) in job.responsibilities" :key="idx">
              {{ responsibility }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ExperienceSection',
  setup() {
    const experiences = [
      {
        position: 'Jr. Dot Developer',
        company: 'Agdova Technologies',
        period: 'Jun 2025 – Present',
        responsibilities: [
          'EBIMS (June 2025 – Present): Built enterprise-level Web API & MVC Core modules for ticketing, support, and overall management with dynamic headers, role-based access, and multi-module integration.',
          'Developed RESTful APIs for seamless data integration across multiple business modules',
          'Implemented role-based authentication and authorization systems',
          'Enhanced application performance and scalability through code optimization'
        ]
      },
      {
        position: 'Web Developer',
        company: 'Embedded Design Services India Pvt Ltd',
        period: 'Oct 2022 – May 2025',
        responsibilities: [
          'Vehicle Tracking System (Jan 2023 – Oct 2023): Rebuilt a legacy vehicle tracking system using ASP.NET MVC (Razor View) and backend, improving performance, UI/UX, and reporting features.',
          'Modernized legacy codebase with current .NET technologies',
          'Improved system performance by 40% through database optimization',
          'Enhanced user interface with responsive design principles'
        ]
      }
    ]
    
    return {
      experiences
    }
  }
}
</script>

<style scoped>
/* Experience section styles will be inherited from global CSS */
</style>
