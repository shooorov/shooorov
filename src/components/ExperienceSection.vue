<script setup>
const experiences = [
  {
    role: 'Software Engineer',
    company: 'Starbase Club',
    location: 'Dhaka',
    duration: '2023 — PRS',
    description: 'Lead developer for enterprise-scale management systems and cloud-native architectures.',
    isCurrent: true
  },
  {
    role: 'Contract Software Developer',
    company: 'ValueToFlow',
    location: 'Remote',
    duration: '2022 — PRS',
    description: 'Providing technical leadership for international software development initiatives.',
    isCurrent: true
  },
  {
    role: 'Junior Web Developer',
    company: 'Datasys Limited',
    location: 'Dhaka',
    duration: '2019 — 2020',
    description: 'Developed core features and handled client integration for fintech applications.',
    isCurrent: false
  }
];
</script>

<template>
  <section class="experience-section section-dark border-top border-bottom" id="experience">
    <div class="container">
      <div class="section-header">
        <span class="mono accent">03 / HISTORY</span>
        <h2 class="section-title">Professional / <br/>Technical Journey</h2>
      </div>
      
      <div class="experience-list">
        <div 
          v-for="(exp, index) in experiences" 
          :key="index" 
          class="exp-item border-top"
          :class="{ 'current': exp.isCurrent }"
        >
          <div class="exp-left">
            <span class="mono exp-year">{{ exp.duration }}</span>
            <span class="mono exp-location">{{ exp.location }}</span>
          </div>
          
          <div class="exp-center">
            <h3 class="exp-role">{{ exp.role }}</h3>
            <p class="exp-company mono">{{ exp.company }}</p>
          </div>
          
          <div class="exp-right">
            <p class="exp-desc">{{ exp.description }}</p>
            <div v-if="exp.isCurrent" class="status-indicator">
              <span class="status-dot"></span>
              <span class="mono">ACTIVE</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.experience-section {
  padding: 8rem 0;
}

.section-header {
  margin-bottom: 5rem;
}

.section-title {
  font-size: 3.5rem;
  margin-top: 1rem;
}

.experience-list {
  display: flex;
  flex-direction: column;
}

.exp-item {
  display: grid;
  grid-template-columns: 200px 1fr 1.5fr;
  padding: 3rem 0;
  gap: 4rem;
  transition: background 0.4s ease;
}

.exp-item:hover {
  background: rgba(255, 255, 255, 0.02);
}

.exp-left {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.exp-year {
  font-size: 0.85rem;
  font-weight: 700;
  color: var(--accent-fin);
}

.exp-location {
  font-size: 0.65rem;
  opacity: 0.5;
}

.exp-role {
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.exp-company {
  font-size: 0.8rem;
  opacity: 0.7;
}

.exp-desc {
  font-size: 1.1rem;
  line-height: 1.6;
  color: var(--text-secondary);
  max-width: 450px;
}

.status-indicator {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-top: 1.5rem;
}

.status-dot {
  width: 6px;
  height: 6px;
  background: var(--accent-fin);
  border-radius: 50%;
  box-shadow: 0 0 10px var(--accent-fin);
}

.status-indicator .mono {
  font-size: 0.6rem;
  letter-spacing: 0.2rem;
  opacity: 0.8;
}

.accent {
  color: var(--accent-fin);
}

@media (max-width: 1024px) {
  .exp-item {
    grid-template-columns: 1fr;
    gap: 1.5rem;
    padding: 2.5rem 0;
  }
  .exp-desc { max-width: 100%; }
}

@media (max-width: 768px) {
  .section-title { font-size: 2.5rem; }
  .exp-role { font-size: 1.5rem; }
}
</style>
