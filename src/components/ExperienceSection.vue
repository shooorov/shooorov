<script setup>
const experiences = [
  {
    role: 'Software Engineer',
    company: 'Starbase Club',
    duration: 'June 2023 - Present',
    description: 'Developing robust web applications and managing backend systems.',
    isCurrent: true
  },
  {
    role: 'Contract Software Developer',
    company: 'Freelance',
    duration: '2021 - Present',
    description: 'Worked with Crebsol Ltd, Datasys Limited, DaVinci Solutions, and ValueToFlow on various contract projects.',
    isCurrent: true
  },
  {
    role: 'Junior Web Developer',
    company: 'Datasys Limited',
    duration: 'October 2019 - June 2020',
    description: 'Built foundational web components and assisted in client project deliveries.',
    isCurrent: false
  }
];
</script>

<template>
  <section class="experience-section" id="experience">
    <div class="container">
      <h2 class="section-title">My <span class="text-gradient-alt">Experience</span></h2>
      
      <div class="timeline">
        <div class="timeline-item" v-for="(exp, index) in experiences" :key="index">
          <div class="timeline-dot" :class="{ 'active': exp.isCurrent }"></div>
          <div class="timeline-content glass-panel">
            <div class="exp-header">
              <h3>{{ exp.role }}</h3>
              <span class="duration">{{ exp.duration }}</span>
            </div>
            <h4 class="company">{{ exp.company }}</h4>
            <p>{{ exp.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.experience-section {
  padding: 5rem 0;
  position: relative;
}

.section-title {
  font-size: 3rem;
  text-align: center;
  margin-bottom: 4rem;
}

.timeline {
  max-width: 800px;
  margin: 0 auto;
  position: relative;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 15px;
  top: 0;
  height: 100%;
  width: 2px;
  background: var(--glass-border);
}

.timeline-item {
  position: relative;
  padding-left: 50px;
  margin-bottom: 3rem;
}

.timeline-dot {
  position: absolute;
  left: 6px;
  top: 5px;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: var(--surface-color-light);
  border: 4px solid var(--laravel-cyan);
  z-index: 1;
}

.timeline-dot.active {
  border-color: var(--neon-green);
  box-shadow: 0 0 15px var(--neon-green);
}

.timeline-content {
  padding: 2rem;
  transition: transform 0.3s ease, border-color 0.3s ease;
}

.timeline-content:hover {
  transform: translateX(10px);
  border-color: var(--electric-blue);
}

.exp-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 0.5rem;
}

.exp-header h3 {
  font-size: 1.5rem;
  color: var(--text-primary);
}

.duration {
  font-size: 0.9rem;
  color: var(--neon-green);
  background: rgba(57, 255, 20, 0.1);
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
}

.company {
  font-size: 1.1rem;
  color: var(--laravel-cyan);
  margin-bottom: 1rem;
}

.timeline-content p {
  color: var(--text-secondary);
  line-height: 1.6;
}

@media (max-width: 600px) {
  .exp-header {
    flex-direction: column;
    gap: 0.5rem;
  }
}
</style>
