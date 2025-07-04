<template>
  <section class="categories-hero">
    <div class="hero-background">
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <div class="container">
          <h1 class="hero-title">Discover Our Collections</h1>
          <p class="hero-subtitle">
            Explore our carefully curated selection of fashion-forward clothing for every style and occasion
          </p>
          <div class="hero-stats">
            <div class="stat-item">
              <span class="stat-number">500+</span>
              <span class="stat-label">Products</span>
            </div>
            <div class="stat-item">
              <span class="stat-number">15</span>
              <span class="stat-label">Categories</span>
            </div>
            <div class="stat-item">
              <span class="stat-number">1000+</span>
              <span class="stat-label">Happy Customers</span>
            </div>
          </div>
          <button class="explore-btn" @click="scrollToCategories">Explore Categories</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'CategoriesHero',
  methods: {
    scrollToCategories() {
      const categoriesSection = document.getElementById('categories-grid');
      if (categoriesSection) {
        categoriesSection.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
}
</script>

<style scoped>
.categories-hero {
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
  background: rgba(0, 0, 0, 0.4);
  z-index: 2;
}

.hero-content {
  position: relative;
  z-index: 3;
  text-align: center;
  color: white;
}

.container {
  max-width: 1000px;
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
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

.hero-stats {
  display: flex;
  justify-content: center;
  gap: 3rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.stat-item {
  text-align: center;
  background: rgba(255, 255, 255, 0.1);
  padding: 1.5rem 2rem;
  border-radius: 15px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.stat-number {
  display: block;
  font-size: 2.5rem;
  font-weight: bold;
  color: #ffffff;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 1.1rem;
  opacity: 0.9;
}

.explore-btn {
  background: #000000;
  color: white;
  padding: 1rem 2.5rem;
  border: none;
  border-radius: 50px;
  font-size: 1.2rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
}

.explore-btn:hover {
  background: #ffffff;
  color: #000000;
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.4);
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-subtitle {
    font-size: 1.1rem;
    margin-bottom: 2rem;
  }
  
  .hero-stats {
    flex-direction: column;
    gap: 1rem;
    align-items: center;
  }
  
  .stat-item {
    width: 200px;
  }
  
  .stat-number {
    font-size: 2rem;
  }
}
</style>