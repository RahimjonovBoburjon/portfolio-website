<template>
  <div id="app" class="bg-navy text-lightest-slate font-calibre">
    <!-- Loader Component -->
    <Loader @loading-complete="onLoadingComplete" />
    
    <!-- Main Content -->
    <div v-show="!isLoading" class="main-content">
      <!-- Navigation -->
      <nav class="fixed top-0 w-full bg-navy/90 backdrop-blur-sm z-50 border-b border-lightest-navy/20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex justify-between items-center h-16">
            <div class="text-green text-xl font-bold nav-logo" data-aos="fade-down" data-aos-delay="200">Portfolio</div>
            <div class="hidden md:flex space-x-8">
              <a href="#about" class="text-lightest-slate hover:text-green transition-colors duration-300 nav-link" data-aos="fade-down" data-aos-delay="300">About</a>
              <a href="#experience" class="text-lightest-slate hover:text-green transition-colors duration-300 nav-link" data-aos="fade-down" data-aos-delay="400">Experience</a>
              <a href="#work" class="text-lightest-slate hover:text-green transition-colors duration-300 nav-link" data-aos="fade-down" data-aos-delay="500">Work</a>
              <a href="#contact" class="text-lightest-slate hover:text-green transition-colors duration-300 nav-link" data-aos="fade-down" data-aos-delay="600">Contact</a>
            </div>
          </div>
        </div>
      </nav>

      <!-- Hero Section -->
      <section class="min-h-screen flex items-center justify-center px-4 pt-16">
        <div class="max-w-4xl mx-auto text-center">
          <p class="text-green mb-4 font-mono text-sm hero-greeting" data-aos="fade-up" data-aos-delay="300">Hi, my name is</p>
          <h1 class="text-6xl md:text-8xl font-bold text-lightest-slate mb-4 leading-tight hero-name" data-aos="fade-up" data-aos-delay="400">
            Your Name
          </h1>
          <h2 class="text-4xl md:text-6xl font-bold text-light-slate mb-8 leading-tight hero-tagline" data-aos="fade-up" data-aos-delay="500">
            I build things for the web.
          </h2>
          <p class="text-xl text-slate max-w-2xl mx-auto mb-12 leading-relaxed hero-description" data-aos="fade-up" data-aos-delay="600">
            I'm a software engineer specializing in building exceptional digital experiences. 
            Currently, I'm focused on building accessible, human-centered products.
          </p>
          <button class="border-2 border-green text-green px-8 py-4 rounded hover:bg-green/10 transition-all duration-300 font-mono text-sm hero-button" 
                  data-aos="fade-up" data-aos-delay="700">
            Check out my work!
          </button>
        </div>
      </section>

      <!-- About Section -->
      <section id="about" class="py-20 px-4">
        <div class="max-w-4xl mx-auto">
          <h2 class="text-3xl font-bold text-lightest-slate mb-12 flex items-center about-title" data-aos="fade-up">
            <span class="text-green mr-4 font-mono text-sm">01.</span>
            About Me
          </h2>
          <div class="grid md:grid-cols-2 gap-12 items-center">
            <div class="about-content">
              <p class="text-slate mb-4 leading-relaxed about-text-1" data-aos="fade-right" data-aos-delay="200">
                Hello! I'm [Your Name], a passionate software engineer with a love for creating 
                beautiful and functional web experiences.
              </p>
              <p class="text-slate mb-4 leading-relaxed about-text-2" data-aos="fade-right" data-aos-delay="300">
                I enjoy creating things that live on the internet, whether that be websites, 
                applications, or anything in between. My goal is to always build products that 
                provide pixel-perfect, performant experiences.
              </p>
              <p class="text-slate mb-4 leading-relaxed about-text-3" data-aos="fade-right" data-aos-delay="400">
                Here are a few technologies I've been working with recently:
              </p>
              <ul class="grid grid-cols-2 gap-2 text-slate about-skills" data-aos="fade-right" data-aos-delay="500">
                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="600">
                  <span class="text-green mr-2">▹</span>
                  JavaScript (ES6+)
                </li>
                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="700">
                  <span class="text-green mr-2">▹</span>
                  Vue.js
                </li>
                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="800">
                  <span class="text-green mr-2">▹</span>
                  React
                </li>
                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="900">
                  <span class="text-green mr-2">▹</span>
                  Node.js
                </li>
                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="1000">
                  <span class="text-green mr-2">▹</span>
                  TypeScript
                </li>
                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="1100">
                  <span class="text-green mr-2">▹</span>
                  Tailwind CSS
                </li>
              </ul>
            </div>
            <div class="relative about-image" data-aos="fade-left" data-aos-delay="400">
              <div class="w-80 h-80 mx-auto bg-lightest-navy rounded-lg relative overflow-hidden">
                <!-- Placeholder for profile image -->
                <div class="absolute inset-0 bg-green/20 rounded-lg"></div>
                <div class="absolute inset-0 border-2 border-green rounded-lg transform translate-x-4 translate-y-4"></div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Experience Section -->
      <section id="experience" class="py-20 px-4">
        <div class="max-w-4xl mx-auto">
          <h2 class="text-3xl font-bold text-lightest-slate mb-12 flex items-center experience-title" data-aos="fade-up">
            <span class="text-green mr-4 font-mono text-sm">02.</span>
            Where I've Worked
          </h2>
          <div class="space-y-8">
            <div class="border-l-2 border-lightest-navy pl-8 experience-item" data-aos="fade-up" data-aos-delay="200">
              <h3 class="text-xl font-bold text-lightest-slate job-title" data-aos="fade-up" data-aos-delay="300">Senior Software Engineer</h3>
              <p class="text-green company-name" data-aos="fade-up" data-aos-delay="400">Company Name</p>
              <p class="text-slate text-sm font-mono job-period" data-aos="fade-up" data-aos-delay="500">2022 - Present</p>
              <ul class="mt-4 space-y-2 text-slate job-description">
                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="600">
                  <span class="text-green mr-2 mt-1">▹</span>
                  Led development of key features for a high-traffic web application
                </li>
                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="700">
                  <span class="text-green mr-2 mt-1">▹</span>
                  Mentored junior developers and conducted code reviews
                </li>
                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="800">
                  <span class="text-green mr-2 mt-1">▹</span>
                  Collaborated with cross-functional teams to deliver exceptional user experiences
                </li>
              </ul>
            </div>
            
            <div class="border-l-2 border-lightest-navy pl-8 experience-item" data-aos="fade-up" data-aos-delay="300">
              <h3 class="text-xl font-bold text-lightest-slate job-title" data-aos="fade-up" data-aos-delay="400">Software Engineer</h3>
              <p class="text-green company-name" data-aos="fade-up" data-aos-delay="500">Previous Company</p>
              <p class="text-slate text-sm font-mono job-period" data-aos="fade-up" data-aos-delay="600">2020 - 2022</p>
              <ul class="mt-4 space-y-2 text-slate job-description">
                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="700">
                  <span class="text-green mr-2 mt-1">▹</span>
                  Built and maintained multiple web applications using modern frameworks
                </li>
                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="800">
                  <span class="text-green mr-2 mt-1">▹</span>
                  Implemented responsive designs and ensured cross-browser compatibility
                </li>
                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="900">
                  <span class="text-green mr-2 mt-1">▹</span>
                  Optimized application performance and user experience
                </li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <!-- Work Section -->
      <section id="work" class="py-20 px-4">
        <div class="max-w-6xl mx-auto">
          <h2 class="text-3xl font-bold text-lightest-slate mb-12 flex items-center work-title" data-aos="fade-up">
            <span class="text-green mr-4 font-mono text-sm">03.</span>
            Some Things I've Built
          </h2>
          <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
            <div class="bg-lightest-navy p-6 rounded-lg hover:transform hover:scale-105 transition-all duration-300 group project-card" data-aos="fade-up" data-aos-delay="200">
              <h3 class="text-xl font-bold text-lightest-slate mb-2 group-hover:text-green transition-colors project-title" data-aos="fade-up" data-aos-delay="300">Project One</h3>
              <p class="text-slate mb-4 leading-relaxed project-description" data-aos="fade-up" data-aos-delay="400">A beautiful web application built with modern technologies.</p>
              <div class="flex flex-wrap gap-2 mb-4 project-tech" data-aos="fade-up" data-aos-delay="500">
                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag" data-aos="fade-up" data-aos-delay="600">Vue.js</span>
                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag" data-aos="fade-up" data-aos-delay="700">Tailwind CSS</span>
                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag" data-aos="fade-up" data-aos-delay="800">Node.js</span>
              </div>
              <div class="flex space-x-4 project-links" data-aos="fade-up" data-aos-delay="900">
                <a href="#" class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">Live Demo</a>
                <a href="#" class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">GitHub</a>
              </div>
            </div>
            
            <div class="bg-lightest-navy p-6 rounded-lg hover:transform hover:scale-105 transition-all duration-300 group project-card" data-aos="fade-up" data-aos-delay="300">
              <h3 class="text-xl font-bold text-lightest-slate mb-2 group-hover:text-green transition-colors project-title" data-aos="fade-up" data-aos-delay="400">Project Two</h3>
              <p class="text-slate mb-4 leading-relaxed project-description" data-aos="fade-up" data-aos-delay="500">An innovative mobile-first responsive design.</p>
              <div class="flex flex-wrap gap-2 mb-4 project-tech" data-aos="fade-up" data-aos-delay="600">
                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag" data-aos="fade-up" data-aos-delay="700">React</span>
                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag" data-aos="fade-up" data-aos-delay="800">TypeScript</span>
                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag" data-aos="fade-up" data-aos-delay="900">Firebase</span>
              </div>
              <div class="flex space-x-4 project-links" data-aos="fade-up" data-aos-delay="1000">
                <a href="#" class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">Live Demo</a>
                <a href="#" class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">GitHub</a>
              </div>
            </div>
            
            <div class="bg-lightest-navy p-6 rounded-lg hover:transform hover:scale-105 transition-all duration-300 group project-card" data-aos="fade-up" data-aos-delay="400">
              <h3 class="text-xl font-bold text-lightest-slate mb-2 group-hover:text-green transition-colors project-title" data-aos="fade-up" data-aos-delay="500">Project Three</h3>
              <p class="text-slate mb-4 leading-relaxed project-description" data-aos="fade-up" data-aos-delay="600">A full-stack application with real-time features.</p>
              <div class="flex flex-wrap gap-2 mb-4 project-tech" data-aos="fade-up" data-aos-delay="700">
                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag" data-aos="fade-up" data-aos-delay="800">Next.js</span>
                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag" data-aos="fade-up" data-aos-delay="900">MongoDB</span>
                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag" data-aos="fade-up" data-aos-delay="1000">Socket.io</span>
              </div>
              <div class="flex space-x-4 project-links" data-aos="fade-up" data-aos-delay="1100">
                <a href="#" class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">Live Demo</a>
                <a href="#" class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">GitHub</a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Contact Section -->
      <section id="contact" class="py-20 px-4">
        <div class="max-w-4xl mx-auto text-center">
          <h2 class="text-3xl font-bold text-lightest-slate mb-8 contact-title" data-aos="fade-up">
            Get In Touch
          </h2>
          <p class="text-slate mb-12 max-w-2xl mx-auto leading-relaxed contact-description" data-aos="fade-up" data-aos-delay="200">
            I'm currently looking for new opportunities. Whether you have a question or just want to say hi, 
            I'll try my best to get back to you!
          </p>
          <button class="border-2 border-green text-green px-8 py-4 rounded hover:bg-green/10 transition-all duration-300 font-mono text-sm contact-button" 
                  data-aos="fade-up" data-aos-delay="300">
            Say Hello
          </button>
        </div>
      </section>

      <!-- Footer -->
      <footer class="py-8 px-4 text-center text-slate">
        <p class="font-mono text-sm footer-text" data-aos="fade-up" data-aos-delay="200">Designed & Built by [Your Name]</p>
      </footer>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
import AOS from 'aos'
import 'aos/dist/aos.css'
import Loader from './components/Loader.vue'

export default {
  name: 'App',
  components: {
    Loader
  },
  setup() {
    const isLoading = ref(true)

    const onLoadingComplete = () => {
      isLoading.value = false
      
      // Wait a bit for the DOM to update, then initialize AOS
      setTimeout(() => {
        AOS.init({
          duration: 800,
          easing: 'ease-out-cubic',
          once: false, // Allow animations to repeat on scroll
          offset: 50,
          delay: 0,
          anchorPlacement: 'top-bottom',
          disable: false
        })
      }, 100)
    }

    return {
      isLoading,
      onLoadingComplete
    }
  }
}
</script>

<style scoped>
/* Custom styles for exact Brittany Chiang design */
.font-mono {
  font-family: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', monospace;
}

/* Hover effects */
.group:hover .group-hover\:text-green {
  color: #64ffda;
}

/* Smooth transitions */
.transition-all {
  transition: all 0.3s ease;
}

/* Main content fade in */
.main-content {
  animation: fadeIn 0.5s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}


</style>