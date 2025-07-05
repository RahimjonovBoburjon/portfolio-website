<template>
  <div id="app" class="bg-navy text-lightest-slate font-calibre">
    <!-- Loader Component -->
    <Loader @loading-complete="onLoadingComplete" />
    
    <!-- Main Content -->
    <div v-show="!isLoading" class="main-content">
      <!-- Fixed Social Media Links (Left Side) -->
      <div class="fixed left-8 bottom-0 z-40 hidden lg:flex flex-col items-center social-links" data-aos="fade-up" data-aos-delay="800">
        <ul class="flex flex-col items-center space-y-6 mb-4">
          <li>
            <a href="https://github.com/yourusername" target="_blank" rel="noopener noreferrer" 
               class="text-slate hover:text-green transition-colors duration-300 social-link">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
            </a>
          </li>
          <li>
            <a href="https://linkedin.com/in/yourusername" target="_blank" rel="noopener noreferrer" 
               class="text-slate hover:text-green transition-colors duration-300 social-link">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
            </a>
          </li>
          <li>
            <a href="https://twitter.com/yourusername" target="_blank" rel="noopener noreferrer" 
               class="text-slate hover:text-green transition-colors duration-300 social-link">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                <path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/>
              </svg>
            </a>
          </li>
          <li>
            <a href="https://instagram.com/yourusername" target="_blank" rel="noopener noreferrer" 
               class="text-slate hover:text-green transition-colors duration-300 social-link">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12.017 0C5.396 0 .029 5.367.029 11.987c0 6.62 5.367 11.987 11.988 11.987 6.62 0 11.987-5.367 11.987-11.987C24.014 5.367 18.637.001 12.017.001zM8.449 16.988c-1.297 0-2.448-.49-3.323-1.297C4.198 14.895 3.708 13.744 3.708 12.447s.49-2.448 1.418-3.323c.875-.807 2.026-1.297 3.323-1.297s2.448.49 3.323 1.297c.928.875 1.418 2.026 1.418 3.323s-.49 2.448-1.418 3.244c-.875.807-2.026 1.297-3.323 1.297zm7.718-1.297c-.875.807-2.026 1.297-3.323 1.297s-2.448-.49-3.323-1.297c-.928-.875-1.418-2.026-1.418-3.244s.49-2.448 1.418-3.323c.875-.807 2.026-1.297 3.323-1.297s2.448.49 3.323 1.297c.928.875 1.418 2.026 1.418 3.323s-.49 2.448-1.418 3.244z"/>
              </svg>
            </a>
          </li>
        </ul>
        <div class="w-px h-24 bg-slate opacity-40"></div>
      </div>

      <!-- Fixed Email Link (Right Side) -->
      <div class="fixed right-8 bottom-0 z-40 hidden lg:flex flex-col items-center email-link" data-aos="fade-up" data-aos-delay="900">
        <div class="flex flex-col items-center space-y-6 mb-4">
          <a href="mailto:your.email@example.com" 
             class="text-slate hover:text-green transition-colors duration-300 writing-mode-vertical">
            your.email@example.com
          </a>
        </div>
        <div class="w-px h-24 bg-slate opacity-40"></div>
      </div>

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

/* Fixed social links and email styling */
.social-links {
  position: fixed;
  left: 2rem;
  bottom: 0;
  z-index: 40;
}

.social-link {
  display: block;
  padding: 0.5rem;
  transition: all 0.3s ease;
}

.social-link:hover {
  transform: translateY(-3px);
}

.email-link {
  position: fixed;
  right: 2rem;
  bottom: 0;
  z-index: 40;
}

.writing-mode-vertical {
  writing-mode: vertical-rl;
  text-orientation: mixed;
  font-family: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', monospace;
  font-size: 0.875rem;
  letter-spacing: 0.1em;
  padding: 1rem 0;
  transition: all 0.3s ease;
}

.writing-mode-vertical:hover {
  transform: translateY(-3px);
}

/* Responsive design for mobile */
@media (max-width: 1024px) {
  .social-links,
  .email-link {
    display: none;
  }
}
</style>