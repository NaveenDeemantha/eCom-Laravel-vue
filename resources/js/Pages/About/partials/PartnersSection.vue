<template>
  <section class="partners-section">
    <div class="container">
      <div class="section-header">
        <h2>Our Trusted Partners</h2>
        <p>Collaborating with industry leaders to bring you the best</p>
      </div>
      
      <div class="partners-grid">
        <div class="partner-category" v-for="(category, index) in partnerCategories" :key="index">
          <h3>{{ category.title }}</h3>
          <p>{{ category.description }}</p>
          <div class="partners-list">
            <div class="partner-card" v-for="partner in category.partners" :key="partner.name">
              <div class="partner-logo">
                <span class="partner-initial">{{ partner.initial }}</span>
              </div>
              <div class="partner-info">
                <h4>{{ partner.name }}</h4>
                <p>{{ partner.description }}</p>
                <div class="partner-stats">
                  <div class="stat">
                    <span class="stat-number">{{ partner.stats.years }}</span>
                    <span class="stat-label">Years</span>
                  </div>
                  <div class="stat">
                    <span class="stat-number">{{ partner.stats.products }}</span>
                    <span class="stat-label">Products</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="partnership-cta">
        <h3>Want to Partner with Us?</h3>
        <p>Join our growing network of trusted partners and expand your reach</p>
        <button class="cta-button">Become a Partner</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'PartnersSection',
  data() {
    return {
      partnerCategories: [
        {
          title: 'Fashion & Lifestyle',
          description: 'Leading brands in fashion, accessories, and lifestyle products',
          partners: [
            {
              name: 'StyleCorp',
              initial: 'SC',
              description: 'Premium fashion and accessories',
              stats: { years: '5', products: '2.5K' }
            },
            {
              name: 'TrendMakers',
              initial: 'TM',
              description: 'Contemporary streetwear and lifestyle',
              stats: { years: '3', products: '1.2K' }
            },
            {
              name: 'LuxuryLine',
              initial: 'LL',
              description: 'High-end luxury fashion',
              stats: { years: '4', products: '800' }
            }
          ]
        },
        {
          title: 'Technology & Electronics',
          description: 'Cutting-edge technology and electronic devices',
          partners: [
            {
              name: 'TechInnovate',
              initial: 'TI',
              description: 'Smart devices and gadgets',
              stats: { years: '6', products: '3.2K' }
            },
            {
              name: 'ElectroMax',
              initial: 'EM',
              description: 'Consumer electronics',
              stats: { years: '4', products: '2.8K' }
            },
            {
              name: 'GadgetPro',
              initial: 'GP',
              description: 'Professional tech equipment',
              stats: { years: '2', products: '950' }
            }
          ]
        },
        {
          title: 'Home & Living',
          description: 'Quality products for home improvement and living spaces',
          partners: [
            {
              name: 'HomeCraft',
              initial: 'HC',
              description: 'Home decor and furniture',
              stats: { years: '5', products: '1.8K' }
            },
            {
              name: 'LivingSpace',
              initial: 'LS',
              description: 'Modern living solutions',
              stats: { years: '3', products: '1.5K' }
            },
            {
              name: 'ComfortZone',
              initial: 'CZ',
              description: 'Comfort and wellness products',
              stats: { years: '4', products: '1.1K' }
            }
          ]
        },
        {
          title: 'Health & Beauty',
          description: 'Wellness, beauty, and personal care products',
          partners: [
            {
              name: 'BeautyFirst',
              initial: 'BF',
              description: 'Skincare and cosmetics',
              stats: { years: '4', products: '2.1K' }
            },
            {
              name: 'WellnessHub',
              initial: 'WH',
              description: 'Health and wellness products',
              stats: { years: '3', products: '1.7K' }
            },
            {
              name: 'NaturalCare',
              initial: 'NC',
              description: 'Organic and natural products',
              stats: { years: '2', products: '680' }
            }
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
.partners-section {
  padding: 5rem 0;
  background: #000000;
  color: #ffffff;
}

.container {
  max-width: 1400px;
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
  color: #ffffff;
}

.section-header p {
  font-size: 1.2rem;
  color: #cccccc;
  max-width: 600px;
  margin: 0 auto;
}

.partners-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(600px, 1fr));
  gap: 3rem;
  margin-bottom: 4rem;
}

.partner-category {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  padding: 2.5rem;
  backdrop-filter: blur(10px);
}

.partner-category h3 {
  font-size: 1.8rem;
  font-weight: bold;
  margin-bottom: 1rem;
  color: #ffffff;
}

.partner-category > p {
  font-size: 1.1rem;
  color: #cccccc;
  margin-bottom: 2rem;
  line-height: 1.6;
}

.partners-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.partner-card {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  padding: 1.5rem;
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid rgba(255, 255, 255, 0.15);
  border-radius: 15px;
  transition: all 0.3s ease;
}

.partner-card:hover {
  transform: translateY(-5px);
  background: rgba(255, 255, 255, 0.12);
  border-color: rgba(255, 255, 255, 0.25);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
}

.partner-logo {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #333333 0%, #666666 100%);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  border: 2px solid rgba(255, 255, 255, 0.2);
}

.partner-initial {
  font-size: 1.2rem;
  font-weight: bold;
  color: #ffffff;
}

.partner-info {
  flex: 1;
}

.partner-info h4 {
  font-size: 1.3rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: #ffffff;
}

.partner-info p {
  font-size: 1rem;
  color: #cccccc;
  margin-bottom: 1rem;
  line-height: 1.5;
}

.partner-stats {
  display: flex;
  gap: 2rem;
}

.stat {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.stat-number {
  font-size: 1.2rem;
  font-weight: bold;
  color: #ffffff;
}

.stat-label {
  font-size: 0.9rem;
  color: #999999;
}

.partnership-cta {
  text-align: center;
  padding: 3rem 2rem;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  backdrop-filter: blur(10px);
}

.partnership-cta h3 {
  font-size: 2rem;
  font-weight: bold;
  margin-bottom: 1rem;
  color: #ffffff;
}

.partnership-cta p {
  font-size: 1.1rem;
  color: #cccccc;
  margin-bottom: 2rem;
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
}

.cta-button {
  background: #ffffff;
  color: #000000;
  border: none;
  padding: 1rem 2rem;
  border-radius: 10px;
  font-size: 1.1rem;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.cta-button:hover {
  background: #f0f0f0;
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(255, 255, 255, 0.2);
}

@media (max-width: 768px) {
  .partners-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .section-header h2 {
    font-size: 2.5rem;
  }
  
  .partner-category {
    padding: 2rem;
  }
  
  .partner-card {
    flex-direction: column;
    text-align: center;
    gap: 1rem;
  }
  
  .partner-stats {
    justify-content: center;
  }
}
</style>
