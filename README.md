# Amit Kumar - Vue.js Portfolio

A modern, responsive portfolio website built with Vue.js 3 and Vite.

## Features

- **Modern Vue.js 3** with Composition API
- **Component-based architecture** for better maintainability
- **Responsive design** that works on all devices
- **Smooth animations** and transitions
- **Interactive elements** like skill bars and particle effects
- **Contact form** with email integration
- **Loading screen** for better UX
- **Sticky navigation** with active section highlighting
- **Back to top button** for easy navigation

## Project Structure

```
src/
├── components/
│   ├── AboutSection.vue
│   ├── BackToTop.vue
│   ├── ContactSection.vue
│   ├── EducationSection.vue
│   ├── ExperienceSection.vue
│   ├── FooterSection.vue
│   ├── HeroSection.vue
│   ├── LoadingScreen.vue
│   ├── Navigation.vue
│   ├── ProjectsSection.vue
│   └── SkillsSection.vue
├── App.vue
├── main.js
└── style.css
```

## Setup Instructions

### Prerequisites
- Node.js (version 16 or higher)
- npm or yarn

### Installation

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Run the development server:**
   ```bash
   npm run dev
   ```

3. **Build for production:**
   ```bash
   npm run build
   ```

4. **Preview the production build:**
   ```bash
   npm run preview
   ```

## Vue.js Features Used

- **Composition API** for better code organization
- **Reactive data** for dynamic content
- **Computed properties** for efficient updates
- **Lifecycle hooks** (onMounted, onUnmounted)
- **Event handling** with @click and @submit
- **Conditional rendering** with v-if and v-for
- **Two-way data binding** with v-model
- **Scoped CSS** for component styling

## Key Improvements from Vanilla JS

1. **Component Reusability**: Each section is a separate component
2. **Reactive Data**: Automatic UI updates when data changes
3. **Better State Management**: Centralized state with reactive properties
4. **Type Safety**: Better development experience with Vue's type system
5. **Modern Build Process**: Vite for faster development and optimized builds
6. **Hot Module Replacement**: Instant updates during development

## Components Overview

### HeroSection.vue
- Particle animation background
- Typewriter effect for the subtitle
- Social media links
- Call-to-action buttons

### Navigation.vue
- Sticky navigation bar
- Active section highlighting
- Smooth scroll to sections

### SkillsSection.vue
- Animated skill bars
- Intersection Observer for triggering animations
- Categorized skills display

### ContactSection.vue
- Contact form with validation
- Email integration
- Contact information cards

### ExperienceSection.vue
- Timeline layout
- Work experience details
- Responsive design

### ProjectsSection.vue
- Project cards with technology tags
- Links to demos and GitHub
- Responsive grid layout

## Customization

### Styling
- All styles are in `src/style.css`
- CSS custom properties for easy theming
- Responsive design with mobile-first approach

### Content
- Edit component data in each `.vue` file
- Update personal information in respective components
- Modify styling variables in `style.css`

### Adding New Sections
1. Create a new component in `src/components/`
2. Import and register in `App.vue`
3. Add to the navigation menu
4. Style as needed

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Performance Optimizations

- Lazy loading for images
- Efficient animations with CSS transforms
- Intersection Observer for scroll-based animations
- Optimized bundle size with Vite

## Deployment

The built files in the `dist` folder can be deployed to any static hosting service:
- Netlify
- Vercel
- GitHub Pages
- AWS S3
- Any web server

## License

MIT License - feel free to use this portfolio as a template for your own projects.
