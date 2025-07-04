<template>
  <section class="about-hero">
    <div class="hero-background">
      <div class="background-pattern"></div>
      <div class="floating-elements">
        <div class="floating-element" v-for="i in 8" :key="i" :style="getFloatingStyle(i)"></div>
      </div>
    </div>
    
    <div class="hero-content">
      <div class="content-wrapper">
        <div class="hero-badge">
          <span class="badge-text">Est. 2018</span>
        </div>
        
        <h1 class="hero-title">
          <span class="title-line">Crafting Digital</span>
          <span class="title-line highlight">Excellence</span>
        </h1>
        
        <p class="hero-subtitle">
          We are innovators, creators, and problem-solvers dedicated to delivering 
          exceptional digital experiences that transform businesses and delight customers.
        </p>
        
        <div class="hero-stats">
          <div class="stat-item">
            <div class="stat-number">5+</div>
            <div class="stat-label">Years Experience</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">50k+</div>
            <div class="stat-label">Happy Customers</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">25</div>
            <div class="stat-label">Countries</div>
          </div>
        </div>
        
        <div class="hero-actions">
          <button class="cta-primary">Our Story</button>
          <button class="cta-secondary">Meet the Team</button>
        </div>
      </div>
      
      <div class="hero-visual">
        <div class="visual-container">
          <img src="/images/about-hero.jpg" alt="Our Team" class="hero-image" />
          <div class="image-overlay">
            <div class="overlay-shape"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AboutHero',
  methods: {
    getFloatingStyle(index) {
      const positions = [
        { top: '10%', left: '10%', animationDelay: '0s' },
        { top: '20%', right: '15%', animationDelay: '2s' },
        { top: '60%', left: '5%', animationDelay: '4s' },
        { top: '70%', right: '20%', animationDelay: '1s' },
        { top: '30%', left: '80%', animationDelay: '3s' },
        { top: '80%', left: '70%', animationDelay: '5s' },
        { top: '15%', left: '60%', animationDelay: '2.5s' },
        { top: '50%', right: '10%', animationDelay: '4.5s' }
      ];
      return positions[index - 1];
    }
  }
}
</script>

<style scoped>
.about-hero {
  min-height: 100vh;
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, #000000 0%, #1a1a1a 50%, #000000 100%);
  display: flex;
  align-items: center;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.background-pattern {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="0.5"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
  opacity: 0.3;
}

.floating-elements {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.floating-element {
  position: absolute;
  width: 4px;
  height: 4px;
  background: rgba(255, 255, 255, 0.3);
  border-radius: 50%;
  animation: float 6s infinite ease-in-out;
}

@keyframes float {
  0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0.3; }
  50% { transform: translateY(-20px) rotate(180deg); opacity: 0.8; }
}

.hero-content {
  position: relative;
  z-index: 2;
  width: 100%;
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.content-wrapper {
  color: white;
}

.hero-badge {
  display: inline-block;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 50px;
  padding: 0.5rem 1.5rem;
  margin-bottom: 2rem;
  animation: slideInLeft 1s ease-out;
}

.badge-text {
  font-size: 0.9rem;
  font-weight: 600;
  color: #ffffff;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.hero-title {
  font-size: 4rem;
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 1.5rem;
  animation: slideInLeft 1s ease-out 0.2s both;
}

.title-line {
  display: block;
}

.title-line.highlight {
  background: linear-gradient(135deg, #ffffff 0%, #cccccc 100%);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  position: relative;
}

.title-line.highlight::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 100px;
  height: 4px;
  background: linear-gradient(135deg, #ffffff 0%, #666666 100%);
  border-radius: 2px;
}

.hero-subtitle {
  font-size: 1.25rem;
  line-height: 1.6;
  color: #cccccc;
  margin-bottom: 2.5rem;
  max-width: 500px;
  animation: slideInLeft 1s ease-out 0.4s both;
}

.hero-stats {
  display: flex;
  gap: 2rem;
  margin-bottom: 3rem;
  animation: slideInLeft 1s ease-out 0.6s both;
}

.stat-item {
  text-align: center;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: bold;
  color: #ffffff;
  line-height: 1;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 0.9rem;
  color: #999999;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  animation: slideInLeft 1s ease-out 0.8s both;
}

.cta-primary, .cta-secondary {
  padding: 1rem 2rem;
  border-radius: 10px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 1px;
  border: none;
}

.cta-primary {
  background: #ffffff;
  color: #000000;
}

.cta-primary:hover {
  background: #f0f0f0;
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(255, 255, 255, 0.2);
}

.cta-secondary {
  background: transparent;
  color: #ffffff;
  border: 2px solid #ffffff;
}

.cta-secondary:hover {
  background: #ffffff;
  color: #000000;
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(255, 255, 255, 0.2);
}

.hero-visual {
  position: relative;
  animation: slideInRight 1s ease-out 0.5s both;
}

.visual-container {
  position: relative;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
}

.hero-image {
  width: 100%;
  height: 500px;
  object-fit: cover;
  object-position: center;
  filter: grayscale(20%) brightness(0.9);
  transition: all 0.3s ease;
}

.visual-container:hover .hero-image {
  transform: scale(1.05);
  filter: grayscale(0%) brightness(1);
}

.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(0, 0, 0, 0.4) 0%, rgba(0, 0, 0, 0.2) 100%);
  pointer-events: none;
}

.overlay-shape {
  position: absolute;
  bottom: -50px;
  right: -50px;
  width: 150px;
  height: 150px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  backdrop-filter: blur(10px);
}

@keyframes slideInLeft {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideInRight {
  from {
    opacity: 0;
    transform: translateX(50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@media (max-width: 768px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-stats {
    justify-content: center;
  }
  
  .hero-actions {
    justify-content: center;
    flex-direction: column;
  }
  
  .hero-visual {
    order: -1;
  }
  
  .hero-image {
    height: 300px;
  }
}
</style>
