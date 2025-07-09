<template>
    <div id="app" class="bg-navy text-lightest-slate font-calibre">
        <!-- Loader Component -->
        <Loader @loading-complete="onLoadingComplete" />

        <!-- Main Content -->
        <div v-show="!isLoading" class="main-content">
            <!-- Fixed Social Media Links (Left Side) -->
            <div class="fixed left-8 bottom-0 z-40 hidden lg:flex flex-col items-center social-links" data-aos="fade-up"
                data-aos-delay="800">
                <ul class="flex flex-col items-center space-y-6 mb-4">
                    <li>
                        <a href="https://github.com/RahimjonovBoburjon" target="_blank" rel="noopener noreferrer"
                            class="text-slate hover:text-green transition-colors duration-300 social-link">
                            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                    d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z" />
                            </svg>
                        </a>
                    </li>
                    <li>
                        <a href="https://www.linkedin.com/in/mentorbobur" target="_blank" rel="noopener noreferrer"
                            class="text-slate hover:text-green transition-colors duration-300 social-link">
                            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                    d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z" />
                            </svg>
                        </a>
                    </li>
                    <li>
                        <a href="https://t.me/mentorbobur" target="_blank" rel="noopener noreferrer"
                            class="text-slate hover:text-green transition-colors duration-300 social-link">
                            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                    d="M9.036 16.572l-.396 3.77c.568 0 .814-.244 1.112-.537l2.664-2.537 5.522 4.03c1.012.558 1.736.264 2.002-.937l3.63-17.06c.332-1.53-.557-2.13-1.54-1.76L1.36 9.27c-1.48.58-1.46 1.41-.252 1.78l4.63 1.45 10.74-6.77c.505-.32.97-.143.59.18z" />
                            </svg>
                        </a>
                    </li>
                    <li>
                        <a href="https://www.instagram.com/mentor_bobur" target="_blank" rel="noopener noreferrer"
                            class="text-slate hover:text-green transition-colors duration-300 social-link">
                            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                    d="M7.75 2h8.5A5.75 5.75 0 0 1 22 7.75v8.5A5.75 5.75 0 0 1 16.25 22h-8.5A5.75 5.75 0 0 1 2 16.25v-8.5A5.75 5.75 0 0 1 7.75 2zm0 1.5A4.25 4.25 0 0 0 3.5 7.75v8.5A4.25 4.25 0 0 0 7.75 20.5h8.5A4.25 4.25 0 0 0 20.5 16.25v-8.5A4.25 4.25 0 0 0 16.25 3.5zm4.25 3.25a5.25 5.25 0 1 1 0 10.5a5.25 5.25 0 0 1 0-10.5zm0 1.5a3.75 3.75 0 1 0 0 7.5a3.75 3.75 0 0 0 0-7.5zm5.25.75a1 1 0 1 1-2 0a1 1 0 0 1 2 0z" />
                            </svg>
                        </a>
                    </li>
                </ul>
                <div class="w-px h-24 bg-slate opacity-40"></div>
            </div>

            <!-- Fixed Email Link (Right Side) -->
            <div class="fixed right-8 bottom-0 z-40 hidden lg:flex flex-col items-center email-link" data-aos="fade-up"
                data-aos-delay="900">
                <div class="flex flex-col items-center space-y-6 mb-4">
                    <a href="mailto:shadow88bob@gmail.com"
                        class="text-slate hover:text-green transition-colors duration-300 writing-mode-vertical">
                        shadow88bob@gmail.com
                    </a>
                </div>
                <div class="w-px h-24 bg-slate opacity-40"></div>
            </div>

            <!-- Navigation -->
            <nav class="fixed top-0 w-full bg-navy/90 backdrop-blur-sm z-50 border-b border-lightest-navy/20">
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                    <div class="flex justify-between items-center h-16">
                        <div class="text-[#64ffda] font-bold tracking-widest text-xl font-mono" data-aos="fade-down"
                            data-aos-delay="200">
                            bobur.dev
                        </div>
                        <div class="hidden md:flex items-center space-x-8">
                            <a href="#about"
                                class="flex items-center font-mono text-sm text-lightest-slate hover:text-green transition-colors duration-300 nav-link font-bold"
                                data-aos="fade-down" data-aos-delay="300">
                                <span class="text-green mr-1">01.</span> About
                            </a>
                            <a href="#experience"
                                class="flex items-center font-mono text-sm text-lightest-slate hover:text-green transition-colors duration-300 nav-link font-bold"
                                data-aos="fade-down" data-aos-delay="400">
                                <span class="text-green mr-1">02.</span> Experience
                            </a>
                            <a href="#work"
                                class="flex items-center font-mono text-sm text-lightest-slate hover:text-green transition-colors duration-300 nav-link font-bold"
                                data-aos="fade-down" data-aos-delay="500">
                                <span class="text-green mr-1">03.</span> Work
                            </a>
                            <a href="#contact"
                                class="flex items-center font-mono text-sm text-lightest-slate hover:text-green transition-colors duration-300 nav-link font-bold"
                                data-aos="fade-down" data-aos-delay="600">
                                <span class="text-green mr-1">04.</span> Contact
                            </a>
                            <a href="/boburjon-cv.pdf" target="_blank" rel="noopener noreferrer"
                                class="ml-6 px-4 py-2 border border-green text-green font-mono text-sm rounded transition-all duration-300 hover:bg-green/10 font-bold"
                                data-aos="fade-down" data-aos-delay="700">
                                Resume
                            </a>
                        </div>
                    </div>
                </div>
            </nav>

            <!-- Hero Section -->
            <section class="min-h-screen flex items-center justify-center px-4 pt-16">
                <div class="max-w-4xl mx-auto text-center">
                    <p class="text-green mb-4 font-mono text-sm hero-greeting" data-aos="fade-up" data-aos-delay="300">
                        Hi, my name is</p>
                    <h1 class="text-6xl md:text-5xl font-bold text-lightest-slate mb-4 leading-tight hero-name"
                        data-aos="fade-up" data-aos-delay="400">
                        Boburjon Rahimjonov.
                    </h1>
                    <h2 class="text-4xl md:text-5xl font-bold text-light-slate mb-8 leading-tight hero-tagline"
                        data-aos="fade-up" data-aos-delay="500">
                        I turn code into experience.
                    </h2>
                    <p class="text-lg text-slate max-w-2xl mx-auto mb-12 leading-relaxed hero-description"
                        data-aos="fade-up" data-aos-delay="600">
                        I’m a senior front-end developer passionate about creating clean, accessible and
                        high-performance websites.
                        Right now, I'm focused on building fast and responsive websites using Vue.js, Tailwind CSS and
                        other modern tools.
                    </p>
                    <a href="#about"
                        class="border-2 border-green text-green px-8 py-4 rounded hover:bg-green/10 transition-all duration-300 font-mono text-sm hero-button inline-block text-center"
                        data-aos="fade-up" data-aos-delay="700">
                        More about me!
                    </a>
                </div>
            </section>

            <!-- About Section -->
            <section id="about" class="py-20 px-4">
                <div class="max-w-4xl mx-auto">
                    <h2 class="text-3xl font-bold text-lightest-slate mb-12 flex items-center about-title"
                        data-aos="fade-up">
                        <span class="text-green mr-4 font-mono text-sm">01.</span>
                        About Me
                    </h2>
                    <div class="grid md:grid-cols-2 gap-12 items-center">
                        <div class="about-content">
                            <p class="text-slate mb-4 leading-relaxed about-text-1" data-aos="fade-right"
                                data-aos-delay="200">
                                Hi! I'm Mr Bobur, a front-end developer passionate about building sleek, responsive, and
                                high-performance websites. My journey into web development began with curiosity —
                                experimenting with layouts and small UI interactions quickly turned into a serious
                                passion for crafting digital experiences.
                            </p>
                            <p class="text-slate mb-4 leading-relaxed about-text-2" data-aos="fade-right"
                                data-aos-delay="300">
                                Since then, I’ve worked on everything from educational platforms to startup prototypes,
                                focusing on modern tools like Vue.js, Tailwind CSS, and Firebase. I’m currently working
                                on Forcera, a platform that helps people stay focused and achieve their goals with AI
                                guidance.
                            </p>
                            <p class="text-slate mb-4 leading-relaxed about-text-3" data-aos="fade-right"
                                data-aos-delay="400">
                                Here are a few technologies I've been working with recently:
                            </p>
                            <ul class="grid grid-cols-2 gap-2 text-slate about-skills" data-aos="fade-right"
                                data-aos-delay="500">
                                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="600">
                                    <span class="text-green mr-2">▹</span>
                                    JavaScript (ES6+)
                                </li>
                                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="700">
                                    <span class="text-green mr-2">▹</span>
                                    Vite
                                </li>
                                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="800">
                                    <span class="text-green mr-2">▹</span>
                                    TypeScript
                                </li>
                                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="900">
                                    <span class="text-green mr-2">▹</span>
                                    Vue.js
                                </li>
                                <li class="flex items-center skill-item" data-aos="fade-right" data-aos-delay="1000">
                                    <span class="text-green mr-2">▹</span>
                                    Firebase
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
                                <div class="absolute inset-0 bg-green/20 rounded-lg"><img src="/profile_pic.png"
                                        alt="profile"></div>
                                <div
                                    class="absolute inset-0 border-2 border-green rounded-lg transform translate-x-4 translate-y-4">
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Experience Section -->
            <section id="experience" class="py-20 px-4">
                <div class="max-w-4xl mx-auto">
                    <h2 class="text-3xl font-bold text-lightest-slate mb-12 flex items-center experience-title"
                        data-aos="fade-up">
                        <span class="text-green mr-4 font-mono text-sm">02.</span>
                        Where I've Worked
                    </h2>
                    <div class="space-y-8">
                        <div class="border-l-2 border-lightest-navy pl-8 experience-item" data-aos="fade-up"
                            data-aos-delay="200">
                            <h3 class="text-xl font-bold text-lightest-slate job-title" data-aos="fade-up"
                                data-aos-delay="300">Senior Front-end Developer</h3>
                            <p class="text-green company-name" data-aos="fade-up" data-aos-delay="400">Freelance</p>
                            <p class="text-slate text-sm font-mono job-period" data-aos="fade-up" data-aos-delay="500">
                                2023 - Present</p>
                            <ul class="mt-4 space-y-2 text-slate job-description">
                                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="600">
                                    <span class="text-green mr-2 mt-1">▹</span>
                                    Delivered modern, responsive websites and web apps for various clients using Vue.js
                                    and Tailwind CSS
                                </li>
                                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="700">
                                    <span class="text-green mr-2 mt-1">▹</span>
                                    Worked on diverse freelance projects, including portfolios, landing pages and admin
                                    dashboards
                                </li>
                                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="800">
                                    <span class="text-green mr-2 mt-1">▹</span>
                                    Managed full project cycles independently — from design to deployment
                                </li>
                            </ul>
                        </div>

                        <div class="border-l-2 border-lightest-navy pl-8 experience-item" data-aos="fade-up"
                            data-aos-delay="300">
                            <h3 class="text-xl font-bold text-lightest-slate job-title" data-aos="fade-up"
                                data-aos-delay="400">Front-end Developer</h3>
                            <p class="text-green company-name" data-aos="fade-up" data-aos-delay="500">at IT-LABS
                            </p>
                            <p class="text-slate text-sm font-mono job-period" data-aos="fade-up" data-aos-delay="600">
                                2021 - 2023</p>
                            <ul class="mt-4 space-y-2 text-slate job-description">
                                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="700">
                                    <span class="text-green mr-2 mt-1">▹</span>
                                    Developed and maintained web applications for corporate clients using Vue.js and
                                    JavaScript
                                </li>
                                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="800">
                                    <span class="text-green mr-2 mt-1">▹</span>
                                    Collaborated with backend and design teams to build scalable and reusable UI
                                    components
                                </li>
                                <li class="flex items-start job-point" data-aos="fade-up" data-aos-delay="900">
                                    <span class="text-green mr-2 mt-1">▹</span>
                                    Actively participated in team code reviews and agile workflows
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Work Section -->
            <section id="work" class="py-20 px-4">
                <div class="max-w-6xl mx-auto">
                    <h2 class="text-3xl font-bold text-lightest-slate mb-12 flex items-center work-title"
                        data-aos="fade-up">
                        <span class="text-green mr-4 font-mono text-sm">03.</span>
                        Some Things I've Built
                    </h2>
                    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                        <div class="bg-lightest-navy p-6 rounded-lg hover:transform hover:scale-105 transition-all duration-300 group project-card"
                            data-aos="fade-up" data-aos-delay="200">
                            <h3 class="text-xl font-bold text-lightest-slate mb-2 group-hover:text-green transition-colors project-title"
                                data-aos="fade-up" data-aos-delay="300">Forcera</h3>
                            <p class="text-slate mb-4 leading-relaxed project-description" data-aos="fade-up"
                                data-aos-delay="400">A modern productivity platform designed for focused goal tracking.
                            </p>
                            <div class="flex flex-wrap gap-2 mb-4 project-tech" data-aos="fade-up" data-aos-delay="500">
                                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag"
                                    data-aos="fade-up" data-aos-delay="600">Vue.js</span>
                                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag"
                                    data-aos="fade-up" data-aos-delay="700">Tailwind CSS</span>
                                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag"
                                    data-aos="fade-up" data-aos-delay="800">Firebase</span>
                            </div>
                            <div class="flex space-x-4 project-links" data-aos="fade-up" data-aos-delay="900">
                                <a href="#"
                                    class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">Live
                                    Demo</a>
                                <a href="#"
                                    class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">GitHub</a>
                            </div>
                        </div>

                        <div class="bg-lightest-navy p-6 rounded-lg hover:transform hover:scale-105 transition-all duration-300 group project-card"
                            data-aos="fade-up" data-aos-delay="300">
                            <h3 class="text-xl font-bold text-lightest-slate mb-2 group-hover:text-green transition-colors project-title"
                                data-aos="fade-up" data-aos-delay="400">Dark Empire Mafia</h3>
                            <p class="text-slate mb-4 leading-relaxed project-description" data-aos="fade-up"
                                data-aos-delay="500">An interactive mafia strategy game with real-time roles and deception.</p>
                            <div class="flex flex-wrap gap-2 mb-4 project-tech" data-aos="fade-up" data-aos-delay="600">
                                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag"
                                    data-aos="fade-up" data-aos-delay="700">Vue.js</span>
                                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag"
                                    data-aos="fade-up" data-aos-delay="800">Socket.IO</span>
                                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag"
                                    data-aos="fade-up" data-aos-delay="900">Node.js</span>
                            </div>
                            <div class="flex space-x-4 project-links" data-aos="fade-up" data-aos-delay="1000">
                                <a href="https://dark-empire-mafia.netlify.app/" target="_blank" rel="noopener noreferrer"
                                    class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">Live
                                    Demo</a>
                                <a href="https://github.com/RahimjonovBoburjon/Dark-Empire-Mafia/" target="_blank" rel="noopener noreferrer"
                                    class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">GitHub</a>
                            </div>
                        </div>

                        <div class="bg-lightest-navy p-6 rounded-lg hover:transform hover:scale-105 transition-all duration-300 group project-card"
                            data-aos="fade-up" data-aos-delay="400">
                            <h3 class="text-xl font-bold text-lightest-slate mb-2 group-hover:text-green transition-colors project-title"
                                data-aos="fade-up" data-aos-delay="500">Resume Builder</h3>
                            <p class="text-slate mb-4 leading-relaxed project-description" data-aos="fade-up"
                                data-aos-delay="600">A fast and simple CV builder with live preview and export.</p>
                            <div class="flex flex-wrap gap-2 mb-4 project-tech" data-aos="fade-up" data-aos-delay="700">
                                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag"
                                    data-aos="fade-up" data-aos-delay="800">Vue 3 + Vite</span>
                                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag"
                                    data-aos="fade-up" data-aos-delay="900">Tailwind CSS</span>
                                <span class="text-xs text-green bg-green/10 px-2 py-1 rounded font-mono tech-tag"
                                    data-aos="fade-up" data-aos-delay="1000">OpenAI API</span>
                            </div>
                            <div class="flex space-x-4 project-links" data-aos="fade-up" data-aos-delay="1100">
                                <a href="https://ai-resume-builder-by-bobur.netlify.app/" target="_blank"
                                    rel="noopener noreferrer"
                                    class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">Live
                                    Demo</a>
                                <a href="https://github.com/RahimjonovBoburjon/AI-Resume-Builder" target="_blank"
                                    rel="noopener noreferrer"
                                    class="text-green hover:text-lightest-slate transition-colors font-mono text-sm">GitHub</a>
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
                    <p class="text-slate mb-12 max-w-2xl mx-auto leading-relaxed contact-description" data-aos="fade-up"
                        data-aos-delay="200">
                        I'm currently looking for new opportunities. Whether you have a question or just want to say hi,
                        I'll try my best to get back to you!
                    </p>
                    <button
                        class="border-2 border-green text-green px-8 py-4 rounded hover:bg-green/10 transition-all duration-300 font-mono text-sm contact-button"
                        data-aos="fade-up" data-aos-delay="300">
                        Say Hello
                    </button>
                </div>
            </section>

            <!-- Footer -->
            <footer class="py-8 px-4 text-center text-slate">
                <p class="font-mono text-sm footer-text">
                    Designed & Built by
                    <a href="https://t.me/justc0der" target="_blank" rel="noopener noreferrer"
                        class="text-green font-bold hover:underline transition-colors duration-300">
                        Boburjon
                    </a>
                </p>
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