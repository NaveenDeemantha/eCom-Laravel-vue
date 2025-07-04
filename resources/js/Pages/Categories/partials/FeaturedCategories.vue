<template>
  <section class="featured-categories">
    <div class="container">
      <div class="section-header">
        <h2>Featured Categories</h2>
        <p>Discover our most popular product categories</p>
      </div>
      
      <div class="categories-showcase">
        <div class="main-category">
          <div class="category-image">
            <img src="/images/imgs3.webp" alt="Fashion" />
          </div>
          <div class="category-content">
            <h3>Fashion & Style</h3>
            <p>Discover the latest trends in fashion with our curated collection of clothing, accessories, and footwear from top brands worldwide.</p>
            <div class="category-stats">
              <div class="stat">
                <span class="stat-number">2,500+</span>
                <span class="stat-label">Products</span>
              </div>
              <div class="stat">
                <span class="stat-number">150+</span>
                <span class="stat-label">Brands</span>
              </div>
              <div class="stat">
                <span class="stat-number">4.8★</span>
                <span class="stat-label">Rating</span>
              </div>
            </div>
            <button class="explore-btn">Explore Fashion</button>
          </div>
        </div>
        
        <div class="secondary-categories">
          <div class="category-card" v-for="category in secondaryCategories" :key="category.name">
            <div class="category-icon">
              <span v-html="category.icon"></span>
            </div>
            <h4>{{ category.name }}</h4>
            <p>{{ category.description }}</p>
            <div class="category-info">
              <span class="product-count">{{ category.productCount }} items</span>
              <span class="price-range">From ${{ category.priceFrom }}</span>
            </div>
          </div>
        </div>
      </div>
      
      <div class="trending-section">
        <h3>Trending Now</h3>
        <div class="trending-tags">
          <span class="trending-tag" v-for="tag in trendingTags" :key="tag">{{ tag }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FeaturedCategories',
  data() {
    return {
      secondaryCategories: [
        {
          name: 'Electronics',
          icon: '📱',
          description: 'Latest gadgets and technology',
          productCount: '1,200',
          priceFrom: '29'
        },
        {
          name: 'Home & Living',
          icon: '🏠',
          description: 'Furniture and home decor',
          productCount: '800',
          priceFrom: '15'
        },
        {
          name: 'Health & Beauty',
          icon: '💄',
          description: 'Skincare and wellness',
          productCount: '950',
          priceFrom: '12'
        },
        {
          name: 'Sports & Fitness',
          icon: '🏃',
          description: 'Athletic wear and equipment',
          productCount: '650',
          priceFrom: '25'
        },
        {
          name: 'Books & Media',
          icon: '📚',
          description: 'Books, games, and entertainment',
          productCount: '450',
          priceFrom: '8'
        },
        {
          name: 'Automotive',
          icon: '🚗',
          description: 'Car accessories and tools',
          productCount: '320',
          priceFrom: '18'
        }
      ],
      trendingTags: [
        'Summer Collection',
        'Smart Home',
        'Sustainable Fashion',
        'Gaming Gear',
        'Fitness Equipment',
        'Organic Skincare',
        'Wireless Tech',
        'Minimalist Design'
      ]
    }
  }
}
</script>

<style scoped>
.featured-categories {
  padding: 5rem 0;
  background: #ffffff;
  color: #333333;
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
  color: #000000;
}

.section-header p {
  font-size: 1.2rem;
  color: #666666;
  max-width: 600px;
  margin: 0 auto;
}

.categories-showcase {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  margin-bottom: 4rem;
}

.main-category {
  display: flex;
  flex-direction: column;
  background: #f8f9fa;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.main-category:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.category-image {
  height: 250px;
  overflow: hidden;
}

.category-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.main-category:hover .category-image img {
  transform: scale(1.05);
}

.category-content {
  padding: 2rem;
}

.category-content h3 {
  font-size: 1.8rem;
  font-weight: bold;
  margin-bottom: 1rem;
  color: #000000;
}

.category-content p {
  font-size: 1.1rem;
  color: #666666;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.category-stats {
  display: flex;
  gap: 2rem;
  margin-bottom: 2rem;
}

.stat {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.stat-number {
  font-size: 1.5rem;
  font-weight: bold;
  color: #000000;
}

.stat-label {
  font-size: 0.9rem;
  color: #666666;
}

.explore-btn {
  background: #000000;
  color: #ffffff;
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

.explore-btn:hover {
  background: #333333;
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
}

.secondary-categories {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
}

.category-card {
  background: #ffffff;
  border: 2px solid #e9ecef;
  border-radius: 15px;
  padding: 1.5rem;
  text-align: center;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.category-card::before {
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

.category-card:hover {
  transform: translateY(-5px);
  border-color: #000000;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
}

.category-card:hover::before {
  opacity: 1;
}

.category-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  position: relative;
  z-index: 1;
}

.category-card h4 {
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: #000000;
  position: relative;
  z-index: 1;
}

.category-card p {
  font-size: 0.9rem;
  color: #666666;
  margin-bottom: 1rem;
  line-height: 1.5;
  position: relative;
  z-index: 1;
}

.category-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.85rem;
  position: relative;
  z-index: 1;
}

.product-count {
  color: #333333;
  font-weight: 500;
}

.price-range {
  color: #000000;
  font-weight: bold;
}

.trending-section {
  text-align: center;
  padding: 3rem 0;
  background: #f8f9fa;
  border-radius: 20px;
  margin-top: 2rem;
}

.trending-section h3 {
  font-size: 2rem;
  font-weight: bold;
  margin-bottom: 2rem;
  color: #000000;
}

.trending-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
}

.trending-tag {
  background: #000000;
  color: #ffffff;
  padding: 0.8rem 1.5rem;
  border-radius: 25px;
  font-size: 0.9rem;
  font-weight: 500;
  transition: all 0.3s ease;
  cursor: pointer;
}

.trending-tag:hover {
  background: #333333;
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

@media (max-width: 768px) {
  .categories-showcase {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .secondary-categories {
    grid-template-columns: 1fr;
  }
  
  .section-header h2 {
    font-size: 2.5rem;
  }
  
  .category-stats {
    justify-content: center;
  }
  
  .trending-tags {
    gap: 0.5rem;
  }
  
  .trending-tag {
    padding: 0.6rem 1.2rem;
    font-size: 0.8rem;
  }
}
</style>
