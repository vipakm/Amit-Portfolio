<template>
  <section id="projects" class="container section-padding">
    <h2>Featured Projects</h2>
    <div class="projects-grid">
      <div 
        v-for="project in projects" 
        :key="project.title"
        class="project-card card"
      >
        <div class="project-image">
          <div class="project-placeholder">
            <i :class="project.icon"></i>
          </div>
        </div>
        <div class="project-content">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
          <div class="tech-stack">
            <span 
              v-for="tech in project.technologies" 
              :key="tech"
              class="tech-tag"
            >
              {{ tech }}
            </span>
          </div>
          <div class="project-links">
            <a 
              v-if="project.demoLink" 
              :href="project.demoLink" 
              class="btn-primary"
              target="_blank"
            >
              View Demo
            </a>
            <a 
              v-if="project.githubLink" 
              :href="project.githubLink" 
              class="btn-secondary"
              target="_blank"
            >
              GitHub
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProjectsSection',
  setup() {
    const projects = [
      {
        title: 'EBIMS - Enterprise Management System',
        description: 'Comprehensive enterprise-level application with ticketing, support, and management modules. Features dynamic headers, role-based access control, and multi-module integration.',
        technologies: ['ASP.NET MVC Core', 'Web API', 'SQL Server', 'Bootstrap'],
        icon: 'fas fa-cogs',
        demoLink: '#',
        githubLink: 'https://github.com/vipakm'
      },
      {
        title: 'Vehicle Tracking System',
        description: 'Rebuilt legacy vehicle tracking system with modern ASP.NET MVC architecture. Improved performance, enhanced UI/UX, and advanced reporting capabilities.',
        technologies: ['ASP.NET MVC', 'Razor Views', 'JavaScript', 'Google Maps API'],
        icon: 'fas fa-map-marker-alt',
        demoLink: '#',
        githubLink: 'https://github.com/vipakm'
      },
      {
        title: 'Data Processing Pipeline',
        description: 'Real-time data processing solution using Azure Data Factory and Databricks for ETL operations, handling large-scale data transformations efficiently.',
        technologies: ['Azure Data Factory', 'Databricks', 'PySpark'],
        icon: 'fas fa-cloud',
        demoLink: null,
        githubLink: null
      }
    ]
    
    return {
      projects
    }
  }
}
</script>

<style scoped>
/* Projects section styles will be inherited from global CSS */
</style>
