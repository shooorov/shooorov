<script setup>
</script>

<template>
  <section id="hero" class="hero-section section-dark border-bottom">
    <div class="container reveal">
      <div class="hero-layout">
        <div class="meta-info">
          <span class="mono accent">01 / INDEX</span>
          <div class="vertical-line"></div>
          <span class="mono">LOCATION / DHAKA, BD</span>
        </div>
        
        <div class="main-content">
          <p class="mono status-line"><span class="status-dot"></span> AVAILABLE FOR NEW OPPORTUNITIES</p>
          <h1 class="hero-name">Md. Anwar <br/>Shahadat</h1>
          <h2 class="hero-title mono">Software Engineer / <span class="accent">Frontend & Backend</span></h2>
          
          <p class="hero-summary">
            Specializing in building robust management systems and high-performance web applications 
            with a focus on technical precision and user-centric design.
          </p>
          
          <div class="hero-actions">
            <a href="#projects" class="btn btn-primary">Explorer Work</a>
            <a href="#contact" class="btn btn-outline">Initiate Contact</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 8rem 0;
}

.hero-layout {
  display: grid;
  grid-template-columns: 120px 1fr;
  gap: 4rem;
}

.meta-info {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  align-items: center;
  padding-top: 1rem;
}

.meta-info .mono {
  writing-mode: vertical-rl;
  text-orientation: mixed;
  transform: rotate(180deg);
  opacity: 0.5;
  font-size: 0.65rem;
}

.vertical-line {
  width: 1px;
  height: 100px;
  background: var(--glass-border);
}

.status-line {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  font-size: 0.7rem;
  margin-bottom: 2rem;
  opacity: 0.7;
}

.status-dot {
  width: 6px;
  height: 6px;
  background: var(--accent-fin);
  border-radius: 50%;
  display: inline-block;
  box-shadow: 0 0 10px var(--accent-fin);
}

.hero-name {
  font-size: 7rem;
  margin-bottom: 1.5rem;
  letter-spacing: -0.02em;
}

.hero-title {
  font-size: 1rem;
  margin-bottom: 3rem;
  opacity: 0.9;
}

.hero-summary {
  max-width: 500px;
  font-size: 1.1rem;
  color: var(--text-secondary);
  margin-bottom: 3rem;
  line-height: 1.8;
}

.hero-actions {
  display: flex;
  gap: 1.5rem;
}

.accent {
  color: var(--accent-fin);
}

@media (max-width: 1024px) {
  .hero-name { font-size: 5rem; }
  .hero-layout { grid-template-columns: 1fr; }
  .meta-info { display: none; }
}

@media (max-width: 768px) {
  .hero-name { font-size: 3.5rem; }
  .hero-actions { flex-direction: column; }
}
</style>
