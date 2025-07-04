<template>
  <section class="values-section">
    <div class="container">
      <div class="section-header">
        <h2>Our Core Values</h2>
        <p>The principles that guide everything we do</p>
      </div>
      
      <div class="values-grid">
        <div class="value-card" v-for="(value, index) in values" :key="index">
          <div class="value-icon">
            <span v-html="value.icon"></span>
          </div>
          <h3>{{ value.title }}</h3>
          <p>{{ value.description }}</p>
          <div class="value-details">
            <ul>
              <li v-for="detail in value.details" :key="detail">{{ detail }}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ValuesSection',
  data() {
    return {
      values: [
        {
          icon: '🎯',
          title: 'Quality First',
          description: 'We never compromise on the quality of our products and services.',
          details: [
            'Rigorous quality control processes',
            'Premium materials and craftsmanship',
            'Continuous improvement standards',
            'Customer satisfaction guarantee'
          ]
        },
        {
          icon: '🌱',
          title: 'Sustainability',
          description: 'Committed to environmental responsibility and ethical practices.',
          details: [
            'Eco-friendly packaging solutions',
            'Carbon-neutral shipping options',
            'Sustainable product sourcing',
            'Waste reduction initiatives'
          ]
        },
        {
          icon: '🤝',
          title: 'Customer Centricity',
          description: 'Our customers are at the heart of everything we do.',
          details: [
            '24/7 customer support',
            'Personalized shopping experience',
            'Responsive feedback system',
            'Community-driven improvements'
          ]
        },
        {
          icon: '💡',
          title: 'Innovation',
          description: 'Continuously evolving to meet the changing needs of our customers.',
          details: [
            'Latest technology integration',
            'Innovative product development',
            'Smart shopping solutions',
            'Future-forward thinking'
          ]
        },
        {
          icon: '🔒',
          title: 'Trust & Security',
          description: 'Building lasting relationships through transparency and security.',
          details: [
            'Secure payment processing',
            'Data privacy protection',
            'Transparent business practices',
            'Reliable service delivery'
          ]
        },
        {
          icon: '🚀',
          title: 'Excellence',
          description: 'Striving for excellence in every aspect of our business.',
          details: [
            'Continuous team training',
            'Performance optimization',
            'Industry best practices',
            'Exceeding expectations'
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
.values-section {
  padding: 5rem 0;
  background: #ffffff;
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

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.value-card {
  background: #f8f9fa;
  border: 2px solid #e9ecef;
  border-radius: 15px;
  padding: 2.5rem 2rem;
  text-align: center;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.value-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(0, 0, 0, 0.02) 0%, rgba(0, 0, 0, 0.05) 100%);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.value-card:hover {
  transform: translateY(-10px);
  border-color: #000000;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.value-card:hover::before {
  opacity: 1;
}

.value-icon {
  font-size: 3rem;
  margin-bottom: 1.5rem;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.1));
}

.value-card h3 {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
  color: #000000;
}

.value-card p {
  font-size: 1.1rem;
  color: #666666;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.value-details {
  text-align: left;
}

.value-details ul {
  list-style: none;
  padding: 0;
}

.value-details li {
  padding: 0.5rem 0;
  color: #333333;
  font-size: 0.95rem;
  position: relative;
  padding-left: 1.5rem;
}

.value-details li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #000000;
  font-weight: bold;
}

@media (max-width: 768px) {
  .values-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .section-header h2 {
    font-size: 2.5rem;
  }
  
  .value-card {
    padding: 2rem 1.5rem;
  }
}
</style>
