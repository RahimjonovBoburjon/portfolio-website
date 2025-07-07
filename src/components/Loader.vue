<template>
  <div v-if="showLoader" class="loader-overlay">
    <transition name="fade-slide">
      <div v-if="showLogo" class="loader-container">
        <div class="loader-logo" :class="{ 'logo-in': logoIn, 'logo-out': logoOut }">
          <div class="logo-text">Crafting</div>
          <div class="logo-dot"></div>
          <div class="logo-dot"></div>
          <div class="logo-dot"></div>
        </div>
        <transition name="fade">
          <div v-if="showBar" class="loader-bar">
            <div class="loader-progress" :class="{ 'progress-full': barFull }"></div>
          </div>
        </transition>
      </div>
    </transition>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'

export default {
  name: 'Loader',
  props: {
    duration: {
      type: Number,
      default: 1200
    }
  },
  emits: ['loading-complete'],
  setup(props, { emit }) {
    const showLoader = ref(true)
    const showLogo = ref(false)
    const showBar = ref(false)
    const barFull = ref(false)
    const logoIn = ref(false)
    const logoOut = ref(false)

    onMounted(() => {
      // Step 1: Animate logo in
      showLogo.value = true
      setTimeout(() => {
        logoIn.value = true
        // Step 2: Show and animate bar
        setTimeout(() => {
          showBar.value = true
          setTimeout(() => {
            barFull.value = true
            // Step 3: Hide bar after fill, keep logo
            setTimeout(() => {
              showBar.value = false
              // Step 4: Animate logo out
              setTimeout(() => {
                logoOut.value = true
                // Step 5: Hide loader after logo out
                setTimeout(() => {
                  showLoader.value = false
                  emit('loading-complete')
                }, 500)
              }, 400)
            }, 400)
          }, props.duration)
        }, 200) // faster initial delay
      }, 50)
    })

    return {
      showLoader,
      showLogo,
      showBar,
      barFull,
      logoIn,
      logoOut
    }
  }
}
</script>

<style scoped>
.loader-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: #0a192f;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
}

.loader-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}

.loader-logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  opacity: 0;
  transform: scale(0.8) translateY(40px);
}

.logo-in {
  animation: logoInAnim 0.7s cubic-bezier(0.4,0,0.2,1) forwards;
}

.logo-out {
  animation: logoOutAnim 0.5s cubic-bezier(0.4,0,0.2,1) forwards;
}

@keyframes logoInAnim {
  0% {
    opacity: 0;
    transform: scale(0.8) translateY(40px);
  }
  60% {
    opacity: 1;
    transform: scale(1.08) translateY(0);
  }
  100% {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}

@keyframes logoOutAnim {
  to {
    opacity: 0;
    transform: scale(0.8) translateY(-40px);
  }
}

.logo-text {
  font-family: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', monospace;
  font-size: 2rem;
  font-weight: bold;
  color: #64ffda;
  letter-spacing: 0.1em;
}

.logo-dot {
  width: 6px;
  height: 6px;
  margin: 0 4px;
  border-radius: 50%;
  background: #64ffda;
  display: inline-block;
  animation: loader-bounce 1s infinite;
}

.logo-dot:nth-child(1) {
  animation-delay: 0s;
}
.logo-dot:nth-child(2) {
  animation-delay: 0.2s;
}
.logo-dot:nth-child(3) {
  animation-delay: 0.4s;
}

@keyframes loader-bounce {
  0%, 80%, 100% {
    transform: scale(1);
    opacity: 0.7;
  }
  40% {
    transform: scale(1.5);
    opacity: 1;
  }
}

.loader-bar {
  width: 200px;
  height: 2px;
  background-color: #233554;
  border-radius: 1px;
  overflow: hidden;
  opacity: 0;
  animation: barIn 0.4s 0.2s cubic-bezier(0.4,0,0.2,1) forwards;
}

@keyframes barIn {
  to {
    opacity: 1;
  }
}

.loader-progress {
  height: 100%;
  background-color: #64ffda;
  border-radius: 1px;
  width: 0%;
  transition: width 1.2s cubic-bezier(0.4,0,0.2,1);
}

.progress-full {
  width: 100%;
}

.fade-slide-enter-active, .fade-slide-leave-active {
  transition: opacity 0.5s, transform 0.5s;
}
.fade-slide-enter-from, .fade-slide-leave-to {
  opacity: 0;
  transform: translateY(40px);
}
.fade-slide-leave-from, .fade-slide-enter-to {
  opacity: 1;
  transform: translateY(0);
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.4s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
.fade-leave-from, .fade-enter-to {
  opacity: 1;
}

/* Responsive design */
@media (max-width: 768px) {
  .logo-text {
    font-size: 1.5rem;
  }
  .loader-bar {
    width: 150px;
  }
}
</style>