<script setup>
</script>

<template>
  <section class="contact-section" id="contact">
    <div class="container">
      <div class="contact-card glass-panel animate-fade-in">
        <h2 class="section-title">Get In <span class="text-gradient">Touch</span></h2>
        <p class="subtitle">I'm always open to discussing new projects, creative ideas or opportunities to be part of your visions.</p>
        
        <div class="contact-grid">
          <div class="contact-info">
            <div class="info-item">
              <span class="icon">📍</span>
              <div>
                <h4>Location</h4>
                <p>Mirpur 2, Dhaka, 1216</p>
              </div>
            </div>
            <div class="info-item">
              <span class="icon">📧</span>
              <div>
                <h4>Email</h4>
                <a href="mailto:shooorov@gmail.com">shooorov@gmail.com</a>
              </div>
            </div>
            <div class="info-item">
              <span class="icon">📱</span>
              <div>
                <h4>Phone / WhatsApp</h4>
                <p>+88 01521 440463 / +88 01717 545043</p>
              </div>
            </div>
          </div>
          
          <div class="social-links">
            <h4>Social Profiles</h4>
            <div class="links-group">
              <a href="https://github.com/shooorov" target="_blank" class="social-btn github">
                 GitHub
              </a>
              <a href="https://www.linkedin.com/in/shooorov" target="_blank" class="social-btn linkedin">
                 LinkedIn
              </a>
            </div>
          </div>
        </div>
        
        <div class="footer-msg">
          <p>© {{ new Date().getFullYear() }} Md. Anwar Shahadat. Built with Vue.js & Laravel Spirit.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-section {
  padding: 5rem 0;
  margin-bottom: 5rem;
}

.contact-card {
  padding: 4rem;
  text-align: center;
}

.section-title {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.subtitle {
  color: var(--text-secondary);
  font-size: 1.1rem;
  max-width: 600px;
  margin: 0 auto 3rem;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  text-align: left;
  max-width: 900px;
  margin: 0 auto;
}

.info-item {
  display: flex;
  gap: 1.5rem;
  margin-bottom: 2rem;
  align-items: flex-start;
}

.icon {
  font-size: 1.5rem;
  background: var(--surface-color-light);
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 12px;
  border: 1px solid var(--glass-border);
}

.info-item h4 {
  color: var(--text-primary);
  margin-bottom: 0.3rem;
}

.info-item p, .info-item a {
  color: var(--text-secondary);
}

.social-links h4 {
  margin-bottom: 1.5rem;
  color: var(--text-primary);
}

.links-group {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.social-btn {
  padding: 1rem 2rem;
  border-radius: 12px;
  font-weight: 600;
  text-align: center;
  transition: all 0.3s ease;
  border: 1px solid var(--glass-border);
  background: var(--surface-color);
  color: var(--text-primary);
}

.social-btn:hover {
  transform: translateY(-3px);
  border-color: var(--electric-blue);
  box-shadow: 0 5px 15px rgba(59, 130, 246, 0.2);
}

.github:hover {
  color: #fff;
  background: #24292e;
}

.linkedin:hover {
  color: #fff;
  background: #0077b5;
}

.footer-msg {
  margin-top: 4rem;
  padding-top: 2rem;
  border-top: 1px solid var(--glass-border);
  color: var(--text-secondary);
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  .contact-card {
    padding: 2rem;
  }
}
</style>
