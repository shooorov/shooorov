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
  <section class="about-section section-light" id="about">
    <div class="container">
      <div class="section-header border-bottom">
        <span class="mono accent">02 / ABOUT ME</span>
        <h2 class="section-title">A focus on performance <br/>and technical excellence.</h2>
      </div>
      
      <div class="about-grid">
        <div class="bio-panel border-right">
          <p class="bio-text">
            I am a Software Engineer based in Mirpur, Dhaka. Currently contributing my expertise at <b>Starbase Club</b>, 
            where I architect and build robust web systems using Laravel and Vue.js.
          </p>
          <p class="bio-text">
            My approach is rooted in computer science fundamentals, grounded by a B.Sc. from BUBT 
            and a history of competitive programming problem-solving.
          </p>
          
          <div class="education-block border-top">
            <h4 class="mono">EDUCATION / CREDENTIALS</h4>
            <div class="edu-item">
              <span class="mono">2018—2022</span>
              <p>B.Sc. in Computer Science & Engineering (CGPA: 3.59)</p>
            </div>
            <div class="edu-item">
              <span class="mono">2016-2018</span>
              <p>HSC & SSC in Science (GPA: 5.00)</p>
            </div>
          </div>
        </div>
        
        <div class="skills-panel">
          <h4 class="mono">CORE / TECHNOLOGIES</h4>
          <div class="skills-grid">
            <div class="skill-item" v-for="skill in skills" :key="skill.name">
              <img :src="`https://skillicons.dev/icons?i=${skill.icon}&theme=light`" :alt="skill.name" />
              <span class="mono">{{ skill.name }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  padding: 8rem 0;
}

.section-header {
  margin-bottom: 4rem;
  padding-bottom: 2rem;
}

.section-title {
  font-size: 3.5rem;
  margin-top: 1rem;
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
}

.bio-panel {
  padding-right: 4rem;
}

.bio-text {
  font-size: 1.25rem;
  line-height: 1.6;
  margin-bottom: 2rem;
  color: var(--text-primary);
}

.education-block {
  margin-top: 3rem;
  padding-top: 2rem;
}

.education-block h4 {
  margin-bottom: 1.5rem;
  opacity: 0.5;
}

.edu-item {
  margin-bottom: 1.5rem;
}

.edu-item span {
  font-size: 0.65rem;
  opacity: 0.6;
  display: block;
  margin-bottom: 0.2rem;
}

.edu-item p {
  font-weight: 500;
}

.skills-panel h4 {
  margin-bottom: 2rem;
  opacity: 0.5;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  gap: 2rem;
}

.skill-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  transition: transform 0.3s ease;
}

.skill-item:hover {
  transform: translateY(-5px);
}

.skill-item img {
  width: 48px;
  height: 48px;
}

.skill-item span {
  font-size: 0.65rem;
  font-weight: 700;
}

.accent {
  color: var(--accent-fin);
}

@media (max-width: 900px) {
  .about-grid { grid-template-columns: 1fr; }
  .bio-panel { padding-right: 0; border-right: none; }
  .section-title { font-size: 2.5rem; }
}
</style>
