<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const navItems = [
  { id: 'hero', name: 'Index', num: '01' },
  { id: 'about', name: 'About', num: '02' },
  { id: 'experience', name: 'History', num: '03' },
  { id: 'projects', name: 'Work', num: '04' },
  { id: 'contact', name: 'Contact', num: '05' }
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
  const totalHeight = document.documentElement.scrollHeight
  const isAtBottom = (scrollTop + viewportHeight) >= (totalHeight - 20)

  // 1. Identify active section based on proximity to center of viewport
  let currentActiveId = navItems[0].id
  navItems.forEach(item => {
    const el = document.getElementById(item.id)
    if (!el) return
    const rect = el.getBoundingClientRect()
    if (rect.top <= viewportHeight * 0.4 && rect.bottom >= viewportHeight * 0.4) {
      currentActiveId = item.id
    }
  })
  activeSection.value = currentActiveId

  // 2. Stepper & Progress Logic
  let hasReachedActive = false
  navItems.forEach(item => {
    if (item.id === activeSection.value || (isAtBottom && item.id === 'contact')) {
      const el = document.getElementById(item.id)
      if (el) {
        const sectionTop = el.offsetTop
        const sectionHeight = el.offsetHeight
        
        let progress = ((scrollTop - (sectionTop - 100)) / sectionHeight) * 100
        
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
  <nav class="fin-navigator">
    <div class="nav-track">
      <div 
        v-for="item in navItems" 
        :key="item.id" 
        class="nav-item"
        :class="{ 'active': activeSection === item.id }"
        @click="scrollToSection(item.id)"
      >
        <div class="label-container">
          <span class="nav-number mono">{{ item.num }}</span>
          <span class="nav-name mono">{{ item.name }}</span>
        </div>
        <div class="indicator-wrapper">
          <div class="indicator-bg">
            <div 
              class="indicator-fill" 
              :style="{ height: progresses[item.id] + '%' }"
            ></div>
          </div>
          <div class="dot"></div>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.fin-navigator {
  position: fixed;
  left: 4rem;
  top: 50%;
  transform: translateY(-50%);
  z-index: 1000;
  height: 400px;
  display: flex;
  align-items: center;
}

.nav-track {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  position: relative;
}

.nav-item {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  cursor: pointer;
  position: relative;
  transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
}

.label-container {
  display: flex;
  gap: 0.5rem;
  opacity: 0.4;
  transition: all 0.4s ease;
  transform: translateX(-10px);
}

.nav-item:hover .label-container,
.nav-item.active .label-container {
  opacity: 1;
  transform: translateX(0);
}

.nav-number {
  color: var(--accent-fin);
}

.nav-name {
  color: var(--text-primary);
  font-weight: 700;
}

.indicator-wrapper {
  position: relative;
  width: 20px;
  height: 60px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.indicator-bg {
  width: 1px;
  height: 100%;
  background: var(--glass-border);
  position: relative;
}

.indicator-fill {
  width: 2px;
  background: var(--accent-fin);
  position: absolute;
  top: 0;
  left: -0.5px;
  transition: height 0.1s linear;
}

.dot {
  width: 4px;
  height: 4px;
  background: var(--text-primary);
  border-radius: 50%;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  opacity: 0.3;
}

.nav-item.active .dot {
  background: var(--accent-fin);
  opacity: 1;
  box-shadow: 0 0 10px var(--accent-fin);
}

@media (max-width: 1200px) {
  .fin-navigator { left: 1.5rem; }
  .label-container { display: none; }
}

@media (max-width: 768px) {
  .fin-navigator { display: none; }
}
</style>
