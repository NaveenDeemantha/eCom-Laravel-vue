<template>
  <section class="timeline-section">
    <div class="container">
      <div class="section-header">
        <h2>Our Journey</h2>
        <p>Milestones that shaped our story</p>
      </div>
      
      <div class="timeline">
        <div class="timeline-item" v-for="(item, index) in timelineItems" :key="index" :class="{ 'right': index % 2 === 1 }">
          <div class="timeline-content">
            <div class="timeline-year">{{ item.year }}</div>
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
            <div class="timeline-achievements">
              <div class="achievement" v-for="achievement in item.achievements" :key="achievement">
                <span class="achievement-icon">{{ achievement.icon }}</span>
                <span class="achievement-text">{{ achievement.text }}</span>
              </div>
            </div>
          </div>
          <div class="timeline-marker"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'TimelineSection',
  data() {
    return {
      timelineItems: [
        {
          year: '2018',
          title: 'The Beginning',
          description: 'Started as a small online store with a vision to revolutionize e-commerce.',
          achievements: [
            { icon: '🏪', text: 'First online store launched' },
            { icon: '📦', text: '100 products in catalog' },
            { icon: '👥', text: '50 customers served' }
          ]
        },
        {
          year: '2019',
          title: 'Growth Phase',
          description: 'Expanded our product range and established key partnerships.',
          achievements: [
            { icon: '🤝', text: '20 brand partnerships' },
            { icon: '📦', text: '1,000+ products' },
            { icon: '🌍', text: 'International shipping' }
          ]
        },
        {
          year: '2020',
          title: 'Digital Transformation',
          description: 'Embraced technology to enhance customer experience during challenging times.',
          achievements: [
            { icon: '📱', text: 'Mobile app launched' },
            { icon: '🤖', text: 'AI-powered recommendations' },
            { icon: '🚚', text: 'Same-day delivery' }
          ]
        },
        {
          year: '2021',
          title: 'Sustainability Focus',
          description: 'Committed to environmental responsibility and sustainable practices.',
          achievements: [
            { icon: '🌱', text: 'Carbon-neutral shipping' },
            { icon: '♻️', text: 'Eco-friendly packaging' },
            { icon: '🏆', text: 'Green business certification' }
          ]
        },
        {
          year: '2022',
          title: 'Market Leadership',
          description: 'Became a leading player in the e-commerce industry.',
          achievements: [
            { icon: '👥', text: '50,000+ customers' },
            { icon: '🌍', text: '25 countries served' },
            { icon: '⭐', text: '98% satisfaction rate' }
          ]
        },
        {
          year: '2023',
          title: 'Innovation & Excellence',
          description: 'Continued to innovate and set new standards in online retail.',
          achievements: [
            { icon: '💎', text: 'Premium service tier' },
            { icon: '🎯', text: 'Personalized shopping' },
            { icon: '🚀', text: 'Advanced logistics' }
          ]
        },
        {
          year: '2024',
          title: 'Future Vision',
          description: 'Looking ahead with ambitious plans for global expansion and innovation.',
          achievements: [
            { icon: '🌟', text: 'Next-gen platform' },
            { icon: '🔮', text: 'AI-driven insights' },
            { icon: '🌐', text: 'Global marketplace' }
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
.timeline-section {
  padding: 5rem 0;
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  color: #333333;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-header h2 {
  font-size: 3rem;
  margin-bottom: 1rem;
  font-weight: bold;
  color: #000000;
}

.section-header p {
  font-size: 1.2rem;
  color: #666666;
  max-width: 600px;
  margin: 0 auto;
}

.timeline {
  position: relative;
  max-width: 1000px;
  margin: 0 auto;
}

.timeline::before {
  content: '';
  position: absolute;
  width: 4px;
  background: linear-gradient(180deg, #000000 0%, #333333 100%);
  top: 0;
  bottom: 0;
  left: 50%;
  margin-left: -2px;
  border-radius: 2px;
}

.timeline-item {
  padding: 1rem 2rem;
  position: relative;
  background-color: inherit;
  width: 50%;
  margin-bottom: 2rem;
}

.timeline-item::after {
  content: '';
  position: absolute;
  width: 20px;
  height: 20px;
  right: -10px;
  background: #000000;
  border: 4px solid #ffffff;
  top: 20px;
  border-radius: 50%;
  z-index: 1;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.timeline-item.right {
  left: 50%;
}

.timeline-item.right::after {
  left: -10px;
}

.timeline-content {
  padding: 2rem;
  background: #ffffff;
  border-radius: 15px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
  border: 2px solid #e9ecef;
  transition: all 0.3s ease;
}

.timeline-content:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.15);
  border-color: #000000;
}

.timeline-year {
  font-size: 2rem;
  font-weight: bold;
  color: #000000;
  margin-bottom: 1rem;
  text-align: center;
  padding: 0.5rem 1rem;
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  border-radius: 10px;
  display: inline-block;
}

.timeline-content h3 {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
  color: #000000;
}

.timeline-content p {
  font-size: 1.1rem;
  color: #666666;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.timeline-achievements {
  display: flex;
  flex-direction: column;
  gap: 0.8rem;
}

.achievement {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.8rem;
  background: #f8f9fa;
  border-radius: 10px;
  transition: all 0.3s ease;
}

.achievement:hover {
  background: #e9ecef;
  transform: translateX(5px);
}

.achievement-icon {
  font-size: 1.2rem;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 35px;
  height: 35px;
  background: #ffffff;
  border-radius: 50%;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.achievement-text {
  font-size: 1rem;
  color: #333333;
  font-weight: 500;
}

/* Mobile Responsive */
@media (max-width: 768px) {
  .timeline::before {
    left: 30px;
  }
  
  .timeline-item {
    width: 100%;
    padding-left: 4rem;
    padding-right: 1rem;
  }
  
  .timeline-item.right {
    left: 0;
  }
  
  .timeline-item::after {
    left: 21px;
  }
  
  .timeline-item.right::after {
    left: 21px;
  }
  
  .section-header h2 {
    font-size: 2.5rem;
  }
  
  .timeline-content {
    padding: 1.5rem;
  }
  
  .timeline-year {
    font-size: 1.5rem;
  }
}
</style>
