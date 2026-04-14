<script setup>
const projects = [
  { 
    id: '01',
    name: 'Apparel Production & POS', 
    desc: 'Bespoke ERP solution for production, export, and inventory.', 
    tech: ['Laravel', 'Vue.js', 'PostgreSQL'] 
  },
  { 
    id: '02',
    name: 'Unified Attendance System', 
    desc: 'Real-time ZKTeco device synchronization and reporting.', 
    tech: ['PHP', 'C++', 'Hardware API'] 
  },
  { 
    id: '03',
    name: 'Enterprise FinAccounting', 
    desc: 'Tailored financial platform for corporate resource management.', 
    tech: ['Vue.js', 'Inertia', 'MySQL'] 
  },
  { 
    id: '04',
    name: 'Healthcare Management', 
    desc: 'Comprehensive patient, appointment, and clinic ecosystem.', 
    tech: ['Laravel', 'Blade', 'Redis'] 
  }
];
</script>

<template>
  <section class="projects-section section-light border-bottom" id="projects">
    <div class="container">
      <div class="section-header">
        <span class="mono accent">04 / WORK</span>
        <h2 class="section-title">Case Studies / <br/>Technical Solutions</h2>
      </div>
      
      <div class="projects-grid">
        <div 
          v-for="project in projects" 
          :key="project.id" 
          class="project-card border-top border-left"
        >
          <div class="project-id mono">{{ project.id }}</div>
          <div class="project-content">
            <h3 class="project-name">{{ project.name }}</h3>
            <p class="project-desc">{{ project.desc }}</p>
            <div class="project-tech">
              <span v-for="t in project.tech" :key="t" class="mono tech-tag">{{ t }}</span>
            </div>
          </div>
          <div class="project-footer border-top">
            <a href="#" class="view-btn mono">VIEW CASE_STUDY <span class="arrow">→</span></a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.projects-section {
  padding: 8rem 0;
}

.section-header {
  margin-bottom: 5rem;
}

.section-title {
  font-size: 3.5rem;
  margin-top: 1rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  border-right: 1px solid var(--glass-border);
  border-bottom: 1px solid var(--glass-border);
}

.project-card {
  padding: 4rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 450px;
  transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
  position: relative;
}

.project-card:hover {
  background: rgba(0, 0, 0, 0.02);
}

.project-id {
  font-size: 0.75rem;
  opacity: 0.3;
  margin-bottom: 2rem;
}

.project-name {
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.project-desc {
  font-size: 1.1rem;
  color: var(--text-secondary);
  line-height: 1.6;
  margin-bottom: 2rem;
}

.project-tech {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.tech-tag {
  font-size: 0.65rem;
  background: var(--bg-light);
  border: 1px solid var(--border-light);
  padding: 0.3rem 0.6rem;
  opacity: 0.7;
}

.project-footer {
  margin-top: 3rem;
  padding-top: 2rem;
}

.view-btn {
  font-size: 0.75rem;
  font-weight: 700;
  display: flex;
  align-items: center;
  gap: 1rem;
}

.view-btn .arrow {
  transition: transform 0.3s ease;
}

.view-btn:hover .arrow {
  transform: translateX(10px);
}

.accent {
  color: var(--accent-fin);
}

@media (max-width: 1024px) {
  .projects-grid { grid-template-columns: 1fr; border-right: none; }
  .project-card { padding: 3rem; min-height: auto; }
}

@media (max-width: 768px) {
  .section-title { font-size: 2.5rem; }
  .project-name { font-size: 2rem; }
}
</style>
