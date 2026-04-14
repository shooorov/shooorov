<script setup>
</script>

<template>
  <section class="contact-section section-dark" id="contact">
    <div class="container border-top border-left border-right reveal">
      <div class="contact-grid">
        <div class="contact-header">
          <span class="mono accent">05 / CONTACT</span>
          <h2 class="section-title">Let's build / <br/>The next system.</h2>
          <p class="contact-subtitle">
            Currently accepting select projects and engineering opportunities. 
            Based in Dhaka, available for global collaboration.
          </p>
          
          <div class="contact-methods border-top">
            <div class="method">
              <span class="mono">EMAIL_LINK</span>
              <a href="mailto:shooorov@gmail.com" class="mono active-link">shooorov@gmail.com</a>
            </div>
            <div class="method">
              <span class="mono">VOICE_COMM</span>
              <p class="mono">+88 01521 440463</p>
            </div>
          </div>
        </div>
        
        <div class="contact-footer border-top">
          <div class="social-links">
            <a href="https://github.com/shooorov" target="_blank" class="mono social-link">GITHUB</a>
            <a href="https://www.linkedin.com/in/shooorov" target="_blank" class="mono social-link">LINKEDIN</a>
            <a href="#" class="mono social-link">TWITTER / X</a>
          </div>
          <div class="copyright mono">
             © 2026 MD. ANWAR SHAHADAT / ALL_RIGHTS_RESERVED
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-section {
  padding: 8rem 0 4rem;
}

.contact-section .container {
  padding: 6rem;
}

.contact-header {
  margin-bottom: 6rem;
}

.section-title {
  font-size: 5rem;
  margin-top: 1.5rem;
  margin-bottom: 2rem;
}

.contact-subtitle {
  font-size: 1.25rem;
  color: var(--text-secondary);
  max-width: 500px;
  line-height: 1.6;
  margin-bottom: 4rem;
}

.contact-methods {
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding-top: 4rem;
  gap: 2rem;
}

.method {
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
}

.method span {
  font-size: 0.65rem;
  opacity: 0.4;
}

.method a, .method p {
  font-size: 1.1rem;
  font-weight: 700;
}

.active-link {
  color: var(--accent-fin);
  position: relative;
  display: inline-block;
}

.active-link::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 100%;
  height: 1px;
  background: var(--accent-fin);
  transform: scaleX(0);
  transform-origin: right;
  transition: transform 0.4s ease;
}

.active-link:hover::after {
  transform: scaleX(1);
  transform-origin: left;
}

.contact-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 4rem;
}

.social-links {
  display: flex;
  gap: 2.5rem;
}

.social-link {
  font-size: 0.7rem;
  font-weight: 700;
  opacity: 0.5;
  transition: opacity 0.3s ease;
}

.social-link:hover {
  opacity: 1;
  color: var(--accent-fin);
}

.copyright {
  font-size: 0.65rem;
  opacity: 0.3;
}

.accent {
  color: var(--accent-fin);
}

@media (max-width: 1024px) {
  .contact-section .container { padding: 4rem 2rem; }
  .section-title { font-size: 3.5rem; }
  .contact-methods { grid-template-columns: 1fr; }
  .contact-footer { flex-direction: column; gap: 3rem; align-items: flex-start; }
}

@media (max-width: 768px) {
  .section-title { font-size: 2.5rem; }
}
</style>
