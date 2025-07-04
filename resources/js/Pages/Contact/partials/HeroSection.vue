<template>
  <section class="contact-hero">
    <div class="hero-background">
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <div class="container">
          <h1 class="hero-title">Get In Touch</h1>
          <p class="hero-subtitle">
            We'd love to hear from you! Whether you have questions, feedback, or need support, 
            we're here to help you every step of the way.
          </p>
          <div class="hero-features">
            <div class="feature-item">
              <i class="icon">📞</i>
              <span>24/7 Support</span>
            </div>
            <div class="feature-item">
              <i class="icon">💬</i>
              <span>Live Chat</span>
            </div>
            <div class="feature-item">
              <i class="icon">📧</i>
              <span>Quick Response</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ContactHero'
}
</script>

<style scoped>
.contact-hero {
  position: relative;
  height: 70vh;
  min-height: 500px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #000000 0%, #333333 100%);
  z-index: 1;
}

.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.3);
  z-index: 2;
}

.hero-content {
  position: relative;
  z-index: 3;
  text-align: center;
  color: white;
}

.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 0 2rem;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.hero-subtitle {
  font-size: 1.3rem;
  margin-bottom: 3rem;
  line-height: 1.6;
  opacity: 0.9;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.hero-features {
  display: flex;
  justify-content: center;
  gap: 3rem;
  flex-wrap: wrap;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(255, 255, 255, 0.1);
  padding: 1rem 1.5rem;
  border-radius: 25px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.icon {
  font-size: 1.5rem;
}

.feature-item span {
  font-size: 1.1rem;
  font-weight: 500;
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-subtitle {
    font-size: 1.1rem;
    margin-bottom: 2rem;
  }
  
  .hero-features {
    flex-direction: column;
    gap: 1rem;
    align-items: center;
  }
  
  .feature-item {
    width: 200px;
    justify-content: center;
  }
}
</style>
