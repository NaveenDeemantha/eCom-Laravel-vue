<template>
  <section class="brands-section">
    <div class="container">
      <div class="section-header">
        <h2>Our Featured Brands</h2>
        <p>Discover premium quality from trusted fashion brands worldwide</p>
      </div>
      
      <div class="brands-carousel">
        <div class="brands-track" :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
          <div v-for="brandGroup in brandGroups" :key="brandGroup.id" class="brands-slide">
            <div class="brands-grid">
              <div v-for="brand in brandGroup.brands" :key="brand.id" class="brand-card">
                <div class="brand-logo">
                  <img :src="brand.logo" :alt="brand.name" />
                </div>
                <div class="brand-info">
                  <h4>{{ brand.name }}</h4>
                  <p>{{ brand.description }}</p>
                  <div class="brand-stats">
                    <span class="stat">{{ brand.products }} Products</span>
                    <span class="stat">{{ brand.rating }}★</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <button class="carousel-btn prev" @click="prevSlide" :disabled="currentSlide === 0">
          ←
        </button>
        <button class="carousel-btn next" @click="nextSlide" :disabled="currentSlide === brandGroups.length - 1">
          →
        </button>
      </div>
      
      <div class="carousel-indicators">
        <button 
          v-for="(group, index) in brandGroups" 
          :key="index"
          class="indicator"
          :class="{ active: currentSlide === index }"
          @click="currentSlide = index"
        ></button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BrandShowcase',
  data() {
    return {
      currentSlide: 0,
      autoplayInterval: null,
      brands: [
        {
          id: 1,
          name: "Urban Style",
          description: "Contemporary fashion for the modern lifestyle",
          logo: "/images/logo1.png",
          products: 125,
          rating: 4.8
        },
        {
          id: 2,
          name: "Classic Threads",
          description: "Timeless elegance and sophisticated design",
          logo: "/images/logo1.png",
          products: 98,
          rating: 4.7
        },
        {
          id: 3,
          name: "Active Wear Co.",
          description: "Performance clothing for active lifestyles",
          logo: "/images/logo1.png",
          products: 156,
          rating: 4.9
        },
        {
          id: 4,
          name: "Premium Basics",
          description: "High-quality essentials for everyday wear",
          logo: "/images/logo1.png",
          products: 87,
          rating: 4.6
        },
        {
          id: 5,
          name: "Trendy Kids",
          description: "Fun and comfortable clothing for children",
          logo: "/images/logo1.png",
          products: 203,
          rating: 4.8
        },
        {
          id: 6,
          name: "Luxury Collection",
          description: "Exclusive designer pieces for special occasions",
          logo: "/images/logo1.png",
          products: 64,
          rating: 4.9
        }
      ]
    }
  },
  computed: {
    brandGroups() {
      const groups = [];
      for (let i = 0; i < this.brands.length; i += 3) {
        groups.push({
          id: i,
          brands: this.brands.slice(i, i + 3)
        });
      }
      return groups;
    }
  },
  mounted() {
    this.startAutoplay();
  },
  beforeUnmount() {
    this.stopAutoplay();
  },
  methods: {
    nextSlide() {
      if (this.currentSlide < this.brandGroups.length - 1) {
        this.currentSlide++;
      }
    },
    
    prevSlide() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      }
    },
    
    startAutoplay() {
      this.autoplayInterval = setInterval(() => {
        if (this.currentSlide < this.brandGroups.length - 1) {
          this.currentSlide++;
        } else {
          this.currentSlide = 0;
        }
      }, 5000);
    },
    
    stopAutoplay() {
      if (this.autoplayInterval) {
        clearInterval(this.autoplayInterval);
      }
    }
  }
}
</script>

<style scoped>
.brands-section {
  padding: 5rem 0;
  background: #f8f9fa;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-header h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  color: #000000;
}

.section-header p {
  font-size: 1.1rem;
  color: #666666;
}

.brands-carousel {
  position: relative;
  overflow: hidden;
  border-radius: 15px;
  margin-bottom: 2rem;
}

.brands-track {
  display: flex;
  transition: transform 0.5s ease;
}

.brands-slide {
  min-width: 100%;
  padding: 2rem;
  background: white;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.brands-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.brand-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 1.5rem;
  border-radius: 10px;
  transition: all 0.3s ease;
}

.brand-card:hover {
  background: #f8f9fa;
  transform: translateY(-5px);
}

.brand-logo {
  width: 80px;
  height: 80px;
  margin-bottom: 1rem;
  background: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.brand-logo img {
  width: 60px;
  height: 60px;
  object-fit: contain;
}

.brand-info h4 {
  margin-bottom: 0.5rem;
  color: #000000;
  font-size: 1.2rem;
}

.brand-info p {
  color: #666666;
  font-size: 0.9rem;
  margin-bottom: 1rem;
  line-height: 1.4;
}

.brand-stats {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.stat {
  font-size: 0.8rem;
  color: #888888;
  background: #f0f0f0;
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
}

.carousel-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(255, 255, 255, 0.9);
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  font-size: 1.5rem;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.carousel-btn:hover:not(:disabled) {
  background: white;
  transform: translateY(-50%) scale(1.1);
}

.carousel-btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.carousel-btn.prev {
  left: 1rem;
}

.carousel-btn.next {
  right: 1rem;
}

.carousel-indicators {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
}

.indicator {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border: none;
  background: #ddd;
  cursor: pointer;
  transition: all 0.3s ease;
}

.indicator.active {
  background: #000000;
  transform: scale(1.2);
}

@media (max-width: 768px) {
  .brands-grid {
    grid-template-columns: 1fr;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
  
  .brands-slide {
    padding: 1rem;
  }
  
  .carousel-btn {
    width: 40px;
    height: 40px;
    font-size: 1.2rem;
  }
}
</style>
