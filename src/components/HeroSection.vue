<script setup>
</script>

<template>
  <section id="hero" class="hero-section glass-panel">
    <div class="container animate-fade-in">
      <div class="hero-content">
        <p class="greeting text-gradient-alt">Hi 👋, I'm</p>
        <h1 class="name">Md. Anwar <span class="text-gradient">Shahadat</span></h1>
        <h2 class="title">A passionate <span class="text-gradient-alt">Software Engineer</span></h2>
        
        <p class="summary">
          My proactive mindset drives me to embrace new challenges and continuously seek knowledge to enhance my contributions. Based in Dhaka, Bangladesh.
        </p>
        
        <div class="cta-group">
          <a href="#projects" class="btn btn-primary">View My Work</a>
          <a href="#contact" class="btn btn-outline">Contact Me</a>
        </div>
      </div>
      
      <div class="hero-graphic">
        <div class="glow-orb blue-orb"></div>
        <div class="glow-orb cyan-orb"></div>
        <div class="glow-orb green-orb"></div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  min-height: 80vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  margin: 2rem;
  border: 1px solid var(--glass-border);
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.hero-content {
  max-width: 600px;
  z-index: 10;
}

.greeting {
  font-size: 1.5rem;
  font-weight: 500;
  margin-bottom: 0.5rem;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.name {
  font-size: 4.5rem;
  margin-bottom: 0.5rem;
  line-height: 1.1;
}

.title {
  font-size: 2.5rem;
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
  font-weight: 400;
}

.summary {
  font-size: 1.2rem;
  color: var(--text-secondary);
  margin-bottom: 2.5rem;
}

.cta-group {
  display: flex;
  gap: 1rem;
}

.hero-graphic {
  position: absolute;
  right: 10%;
  top: 50%;
  transform: translateY(-50%);
  width: 400px;
  height: 400px;
  z-index: 0;
}

.glow-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(100px);
  opacity: 0.3;
  animation: float 8s ease-in-out infinite both alternate;
}

.blue-orb {
  width: 300px;
  height: 300px;
  background: var(--electric-blue);
  top: 0;
  left: 0;
  animation-delay: 0s;
}

.cyan-orb {
  width: 250px;
  height: 250px;
  background: var(--laravel-cyan);
  bottom: 0;
  right: 0;
  animation-delay: 2s;
}

.green-orb {
  width: 200px;
  height: 200px;
  background: var(--neon-green);
  top: 30%;
  left: 20%;
  animation-delay: 4s;
}

@keyframes float {
  0% { transform: translateY(0) scale(1); }
  100% { transform: translateY(-20px) scale(1.1); }
}

@media (max-width: 900px) {
  .name { font-size: 3rem; }
  .title { font-size: 1.8rem; }
  .hero-graphic { opacity: 0.3; right: -20%; }
}
</style>
