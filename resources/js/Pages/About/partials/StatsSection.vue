<template>
  <section class="stats-section">
    <div class="container">
      <div class="section-header">
        <h2>Our Achievements</h2>
        <p>Numbers that speak for our success and commitment to excellence</p>
      </div>
      
      <div class="stats-grid">
        <div class="stat-card" v-for="(stat, index) in stats" :key="index" :style="{ animationDelay: `${index * 0.2}s` }">
          <div class="stat-icon">
            <span v-html="stat.icon"></span>
          </div>
          <div class="stat-number" ref="statNumbers" :data-target="stat.number">0</div>
          <div class="stat-label">{{ stat.label }}</div>
          <div class="stat-description">{{ stat.description }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'StatsSection',
  data() {
    return {
      stats: [
        {
          icon: '👥',
          number: 50000,
          label: 'Happy Customers',
          description: 'Satisfied customers worldwide'
        },
        {
          icon: '📦',
          number: 250000,
          label: 'Products Sold',
          description: 'Items delivered successfully'
        },
        {
          icon: '🌍',
          number: 25,
          label: 'Countries Served',
          description: 'Global shipping coverage'
        },
        {
          icon: '⭐',
          number: 98,
          label: 'Customer Satisfaction',
          description: 'Average satisfaction rate'
        },
        {
          icon: '🏪',
          number: 500,
          label: 'Brand Partners',
          description: 'Trusted brand collaborations'
        },
        {
          icon: '🚚',
          number: 99,
          label: 'On-Time Delivery',
          description: 'Delivery success rate'
        }
      ]
    }
  },
  mounted() {
    this.animateNumbers();
    this.observeStats();
  },
  methods: {
    animateNumbers() {
      const numbers = this.$refs.statNumbers;
      if (!numbers) return;
      
      numbers.forEach((number, index) => {
        const target = parseInt(number.dataset.target);
        const duration = 2000;
        const step = target / (duration / 50);
        let current = 0;
        
        const timer = setInterval(() => {
          current += step;
          if (current >= target) {
            current = target;
            clearInterval(timer);
          }
          
          if (target > 1000) {
            number.textContent = Math.floor(current).toLocaleString() + '+';
          } else {
            number.textContent = Math.floor(current) + '%';
          }
        }, 50);
      });
    },
    
    observeStats() {
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('animate');
          }
        });
      }, { threshold: 0.1 });
      
      document.querySelectorAll('.stat-card').forEach(card => {
        observer.observe(card);
      });
    }
  }
}
</script>

<style scoped>
.stats-section {
  padding: 5rem 0;
  background: linear-gradient(135deg, #000000 0%, #333333 100%);
  color: white;
  position: relative;
  overflow: hidden;
}

.stats-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="0.5"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
  opacity: 0.3;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 1;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-header h2 {
  font-size: 3rem;
  margin-bottom: 1rem;
  font-weight: bold;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.section-header p {
  font-size: 1.2rem;
  opacity: 0.9;
  max-width: 600px;
  margin: 0 auto;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.stat-card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 20px;
  padding: 2.5rem 2rem;
  text-align: center;
  transition: all 0.3s ease;
  transform: translateY(50px);
  opacity: 0;
  animation: slideUp 0.8s ease forwards;
}

.stat-card:hover {
  transform: translateY(-10px);
  background: rgba(255, 255, 255, 0.15);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
}

.stat-card.animate {
  transform: translateY(0);
  opacity: 1;
}

.stat-icon {
  font-size: 3rem;
  margin-bottom: 1.5rem;
  filter: drop-shadow(0 4px 8px rgba(0, 0, 0, 0.3));
}

.stat-number {
  font-size: 3.5rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: #ffffff;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
  line-height: 1;
}

.stat-label {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: #ffffff;
}

.stat-description {
  font-size: 1rem;
  opacity: 0.8;
  color: #f0f0f0;
}

@keyframes slideUp {
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

@media (max-width: 768px) {
  .stats-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .section-header h2 {
    font-size: 2.5rem;
  }
  
  .stat-card {
    padding: 2rem 1.5rem;
  }
  
  .stat-number {
    font-size: 3rem;
  }
}
</style>
