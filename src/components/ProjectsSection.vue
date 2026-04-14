<script setup>
const projects = [
  { name: 'Apparel Production & POS', desc: 'Complete solution including production workflow, export tracking, and POS.', category: 'ERP' },
  { name: 'Attendance Management', desc: 'Integrated with ZKTeco Devices for live attendance tracking.', category: 'Integration' },
  { name: 'Accounting System (Vue.js)', desc: 'Tailored for business-level financial operations.', category: 'Finance' },
  { name: 'Restaurant POS (Vue.js)', desc: 'Order, billing, inventory, and reporting in one platform.', category: 'POS' },
  { name: 'Doctor Chamber System', desc: 'Patient, appointment, and billing management.', category: 'Healthcare' },
  { name: 'FutSal Sports Management', desc: 'Integrated with Multiple Authentication (React.js).', category: 'Management' },
  { name: 'University Management', desc: 'Trust University & PSTU Convocation Management System.', category: 'Education' },
  { name: 'GariSeba', desc: 'Online Car Renting Service with vehicle & booking management.', category: 'Booking' },
  { name: 'Upside Down BD', desc: 'Online ticket booking and management platform.', category: 'Ticketing' }
];
</script>

<template>
  <section class="projects-section" id="projects">
    <div class="container">
      <h2 class="section-title">Significant <span class="text-gradient">Projects</span></h2>
      <p class="subtitle">A collection of massive management systems built with Laravel & Vue.js</p>
      
      <div class="projects-grid">
        <div class="project-card glass-panel" v-for="(project, index) in projects" :key="index">
          <div class="category-badge">{{ project.category }}</div>
          <h3>{{ project.name }}</h3>
          <p>{{ project.desc }}</p>
          <div class="tech-stack">
            <span class="tech">Laravel</span>
            <span class="tech">Vue.js</span>
            <span class="tech">MySQL</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.projects-section {
  padding: 5rem 0;
}

.section-title {
  font-size: 3rem;
  text-align: center;
  margin-bottom: 1rem;
}

.subtitle {
  text-align: center;
  color: var(--text-secondary);
  font-size: 1.2rem;
  margin-bottom: 4rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
}

.project-card {
  padding: 2rem;
  position: relative;
  transition: all 0.3s ease;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.project-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: var(--gradient-main);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.4s ease;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

.project-card:hover::before {
  transform: scaleX(1);
}

.category-badge {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: rgba(34, 211, 238, 0.1);
  color: var(--laravel-cyan);
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 600;
  letter-spacing: 1px;
}

h3 {
  font-size: 1.3rem;
  margin-top: 1.5rem;
  margin-bottom: 1rem;
  color: var(--text-primary);
}

p {
  color: var(--text-secondary);
  font-size: 0.95rem;
  margin-bottom: 2rem;
  flex-grow: 1;
}

.tech-stack {
  display: flex;
  gap: 0.8rem;
  flex-wrap: wrap;
}

.tech {
  font-size: 0.8rem;
  color: var(--neon-green);
  border: 1px solid rgba(57, 255, 20, 0.3);
  padding: 0.2rem 0.6rem;
  border-radius: 4px;
}
</style>
