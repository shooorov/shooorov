<script setup>
const skills = [
  { name: 'JavaScript', icon: 'js' },
  { name: 'Vue.js', icon: 'vue' },
  { name: 'PHP', icon: 'php' },
  { name: 'Laravel', icon: 'laravel' },
  { name: 'MySQL', icon: 'mysql' },
  { name: 'C++', icon: 'cpp' },
  { name: 'Tailwind CSS', icon: 'tailwind' },
  { name: 'Git', icon: 'git' }
]
</script>

<template>
  <section class="about-section" id="about">
    <div class="container">
      <h2 class="section-title">About <span class="text-gradient">Me</span></h2>
      
      <div class="about-content">
        <div class="bio glass-panel">
          <h3>My Background</h3>
          <p>
            I am a Software Engineer currently working at Starbase Club. I specialize in building 
            robust web applications and complete management systems using <b>Laravel</b> and <b>Vue.js</b>.
          </p>
          <p>
            With a B.Sc. in CSE from Bangladesh University of Business and Technology, I have a strong 
            foundation in logic and problem-solving, having solved over 100+ problems on Uva Online Judge.
          </p>
          <div class="education">
            <h4>Education</h4>
            <ul>
              <li><b>B.Sc. in CSE</b> - BUBT (CGPA: 3.59)</li>
              <li><b>HSC & SSC in Science</b> - Cantonment Public School & College (GPA: 5.00)</li>
            </ul>
          </div>
        </div>
        
        <div class="skills glass-panel">
          <h3>Tech Stack</h3>
          <div class="skills-grid">
            <div class="skill-item" v-for="skill in skills" :key="skill.name">
              <img :src="`https://skillicons.dev/icons?i=${skill.icon}&theme=light`" :alt="skill.name" />
              <span>{{ skill.name }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  padding: 5rem 0;
}

.section-title {
  font-size: 3rem;
  text-align: center;
  margin-bottom: 3rem;
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
}

.bio, .skills {
  padding: 2.5rem;
}

h3 {
  font-size: 1.8rem;
  margin-bottom: 1.5rem;
  color: var(--laravel-cyan);
}

.bio p {
  margin-bottom: 1rem;
  color: var(--text-secondary);
  font-size: 1.1rem;
}

.education {
  margin-top: 2rem;
  padding-top: 1.5rem;
  border-top: 1px solid var(--glass-border);
}

.education h4 {
  color: var(--neon-green);
  margin-bottom: 1rem;
}

.education ul {
  list-style-type: none;
  color: var(--text-secondary);
}

.education li {
  margin-bottom: 0.5rem;
  position: relative;
  padding-left: 1.5rem;
}

.education li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: var(--laravel-cyan);
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  gap: 1.5rem;
  text-align: center;
}

.skill-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  transition: transform 0.3s ease;
}

.skill-item:hover {
  transform: translateY(-5px);
}

.skill-item img {
  width: 50px;
  height: 50px;
  filter: drop-shadow(0 4px 6px rgba(0,0,0,0.3));
}

.skill-item span {
  font-size: 0.9rem;
  color: var(--text-secondary);
  font-weight: 500;
}

@media (max-width: 768px) {
  .about-content {
    grid-template-columns: 1fr;
  }
}
</style>
