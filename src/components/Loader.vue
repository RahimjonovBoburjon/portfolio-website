<template>
  <div v-if="isLoading" class="loader-overlay">
    <div class="loader-container">
      <div class="loader-logo">
        <div class="logo-text">Portfolio</div>
        <div class="logo-dot"></div>
      </div>
      <div class="loader-bar">
        <div class="loader-progress"></div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'

export default {
  name: 'Loader',
  props: {
    duration: {
      type: Number,
      default: 2000
    }
  },
  emits: ['loading-complete'],
  setup(props, { emit }) {
    const isLoading = ref(true)

    onMounted(() => {
      // Simulate loading time
      setTimeout(() => {
        isLoading.value = false
        emit('loading-complete')
      }, props.duration)
    })

    return {
      isLoading
    }
  }
}
</script>

<style scoped>
.loader-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #0a192f;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
  animation: fadeOut 0.5s ease-out 2s forwards;
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
}

.logo-text {
  font-family: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', monospace;
  font-size: 2rem;
  font-weight: bold;
  color: #64ffda;
  letter-spacing: 0.1em;
}

.logo-dot {
  width: 8px;
  height: 8px;
  background-color: #64ffda;
  border-radius: 50%;
  animation: pulse 1.5s ease-in-out infinite;
}

.loader-bar {
  width: 200px;
  height: 2px;
  background-color: #233554;
  border-radius: 1px;
  overflow: hidden;
}

.loader-progress {
  height: 100%;
  background-color: #64ffda;
  border-radius: 1px;
  animation: progress 2s ease-in-out forwards;
}

@keyframes progress {
  0% {
    width: 0%;
  }
  100% {
    width: 100%;
  }
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(1.2);
  }
}

@keyframes fadeOut {
  0% {
    opacity: 1;
    visibility: visible;
  }
  100% {
    opacity: 0;
    visibility: hidden;
  }
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