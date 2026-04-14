<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const navItems = [
  { id: 'hero', name: 'Home' },
  { id: 'about', name: 'About' },
  { id: 'experience', name: 'Experience' },
  { id: 'projects', name: 'Projects' },
  { id: 'contact', name: 'Contact' }
]

const activeSection = ref('hero')
const progresses = ref({
  hero: 0,
  about: 0,
  experience: 0,
  projects: 0,
  contact: 0
})

const calculateProgress = () => {
  const scrollTop = window.scrollY
  const viewportHeight = window.innerHeight

  // 1. Identify active section based on proximity to center of viewport
  let currentActiveId = navItems[0].id
  navItems.forEach(item => {
    const el = document.getElementById(item.id)
    if (!el) return
    const rect = el.getBoundingClientRect()
    // If the section's top is in the upper half or it covers the middle
    if (rect.top <= viewportHeight * 0.4 && rect.bottom >= viewportHeight * 0.4) {
      currentActiveId = item.id
    }
  })
  activeSection.value = currentActiveId

  // 2. Stepper Logic: 100% for past, dynamic for current, 0% for future
  let hasReachedActive = false
  const totalHeight = document.documentElement.scrollHeight
  const isAtBottom = (scrollTop + viewportHeight) >= (totalHeight - 20)

  navItems.forEach(item => {
    if (item.id === activeSection.value || (isAtBottom && item.id === 'contact')) {
      const el = document.getElementById(item.id)
      if (el) {
        const sectionTop = el.offsetTop
        const sectionHeight = el.offsetHeight
        
        let progress = ((scrollTop - (sectionTop - 100)) / sectionHeight) * 100
        
        // Force 100% if we are at the bottom for the contact section
        if (isAtBottom && item.id === 'contact') {
          progress = 100
          activeSection.value = 'contact'
        }
        
        progresses.value[item.id] = Math.max(0, Math.min(100, progress))
      }
      hasReachedActive = true
    } else {
      progresses.value[item.id] = hasReachedActive ? 0 : 100
    }
  })
}

const scrollToSection = (id) => {
  const el = document.getElementById(id)
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' })
  }
}

onMounted(() => {
  window.addEventListener('scroll', calculateProgress)
  window.addEventListener('resize', calculateProgress)
  calculateProgress()
})

onUnmounted(() => {
  window.removeEventListener('scroll', calculateProgress)
  window.removeEventListener('resize', calculateProgress)
})
</script>

<template>
  <nav class="section-navigator">
    <div 
      v-for="item in navItems" 
      :key="item.id" 
      class="nav-item"
      :class="{ 'active': activeSection === item.id }"
      @click="scrollToSection(item.id)"
    >
      <div class="title-container">
        <span class="nav-title">{{ item.name }}</span>
        <div class="progress-bar-bg">
          <div 
            class="progress-bar-fill" 
            :style="{ width: progresses[item.id] + '%' }"
          ></div>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.section-navigator {
  position: fixed;
  left: 3rem;
  top: 50%;
  transform: translateY(-50%);
  z-index: 1000;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  padding: 1.5rem;
  background: rgba(255, 255, 255, 0.6);
  backdrop-filter: blur(12px);
  border-radius: 24px;
  border: 1px solid rgba(0, 0, 0, 0.05);
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.03);
}

.nav-item {
  cursor: pointer;
  transition: all 0.3s ease;
  width: 140px;
}

.title-container {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.nav-title {
  font-size: 0.85rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: var(--text-secondary);
  transition: all 0.3s ease;
}

.nav-item.active .nav-title {
  color: var(--laravel-cyan);
  transform: translateX(5px);
}

.progress-bar-bg {
  width: 100%;
  height: 2px; /* Slightly thinner for a classier look */
  background: rgba(15, 23, 42, 0.03);
  border-radius: 2px;
  overflow: hidden;
  position: relative;
}

.progress-bar-fill {
  height: 100%;
  background: var(--gradient-main);
  border-radius: 1px;
  transition: width 0.05s linear; /* Faster transition for responsive feel */
  box-shadow: 0 0 8px rgba(34, 211, 238, 0.4);
}

.nav-item.active .progress-bar-fill {
  background: var(--gradient-glow);
  box-shadow: 0 0 10px rgba(57, 255, 20, 0.5);
  height: 3px; /* Slightly thicker active line */
}

.nav-item:hover .nav-title {
  color: var(--text-primary);
}

@media (max-width: 1200px) {
  .section-navigator {
    left: 1rem;
    padding: 1rem;
  }
  .nav-item {
    width: 110px;
  }
}

@media (max-width: 768px) {
  .section-navigator {
    display: none;
  }
}
</style>
