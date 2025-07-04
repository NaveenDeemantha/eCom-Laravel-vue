<template>
  <section id="categories-grid" class="categories-section">
    <div class="container">
      <div class="section-header">
        <h2>Shop by Category</h2>
        <p>Discover our wide range of fashion categories designed for every style and occasion</p>
      </div>
      
      <div class="categories-grid">
        <div 
          v-for="category in categories" 
          :key="category.id" 
          class="category-card"
          @click="selectCategory(category)"
        >
          <div class="category-image">
            <img :src="category.image" :alt="category.name" />
            <div class="category-overlay">
              <div class="category-info">
                <h3>{{ category.name }}</h3>
                <p>{{ category.itemCount }} items</p>
                <span class="shop-now">Shop Now →</span>
              </div>
            </div>
          </div>
          <div class="category-details">
            <h4>{{ category.name }}</h4>
            <p class="category-description">{{ category.description }}</p>
            <div class="category-meta">
              <span class="price-range">From ${{ category.priceRange.min }}</span>
              <span class="item-count">{{ category.itemCount }} items</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'CategoriesGrid',
  data() {
    return {
      categories: [
        {
          id: 1,
          name: "Men's Clothing",
          description: "Stylish and comfortable clothing for the modern man",
          image: "/images/imgs2.webp",
          itemCount: 125,
          priceRange: { min: 25, max: 150 }
        },
        {
          id: 2,
          name: "Women's Fashion",
          description: "Elegant and trendy outfits for every occasion",
          image: "/images/imgs3.webp",
          itemCount: 198,
          priceRange: { min: 30, max: 200 }
        },
        {
          id: 3,
          name: "Kids' Wear",
          description: "Comfortable and fun clothing for children",
          image: "/images/imgs4.webp",
          itemCount: 87,
          priceRange: { min: 15, max: 80 }
        },
        {
          id: 4,
          name: "Activewear",
          description: "Performance clothing for fitness and sports",
          image: "/images/imgs5.webp",
          itemCount: 156,
          priceRange: { min: 35, max: 120 }
        },
        {
          id: 5,
          name: "Accessories",
          description: "Complete your look with our premium accessories",
          image: "/images/imgs6.webp",
          itemCount: 94,
          priceRange: { min: 10, max: 75 }
        },
        {
          id: 6,
          name: "Footwear",
          description: "Comfortable and stylish shoes for every step",
          image: "/images/imgs7.webp",
          itemCount: 112,
          priceRange: { min: 45, max: 250 }
        },
        {
          id: 7,
          name: "Formal Wear",
          description: "Professional attire for business and special events",
          image: "/images/imgs8.webp",
          itemCount: 73,
          priceRange: { min: 80, max: 300 }
        },
        {
          id: 8,
          name: "Seasonal",
          description: "Weather-appropriate clothing for all seasons",
          image: "/images/imgs9.webp",
          itemCount: 89,
          priceRange: { min: 25, max: 180 }
        }
      ]
    }
  },
  methods: {
    selectCategory(category) {
      this.$emit('category-selected', category);
      // Scroll to products section
      const productsSection = document.getElementById('products-section');
      if (productsSection) {
        productsSection.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
}
</script>

<style scoped>
.categories-section {
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
  margin-bottom: 4rem;
}

.section-header h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  color: #000000;
}

.section-header p {
  font-size: 1.1rem;
  color: #666666;
  max-width: 600px;
  margin: 0 auto;
}

.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.category-card {
  background: white;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  cursor: pointer;
}

.category-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
}

.category-image {
  position: relative;
  height: 250px;
  overflow: hidden;
}

.category-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.category-card:hover .category-image img {
  transform: scale(1.05);
}

.category-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.4);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.category-card:hover .category-overlay {
  opacity: 1;
}

.category-info {
  text-align: center;
  color: white;
}

.category-info h3 {
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
}

.category-info p {
  margin-bottom: 1rem;
  opacity: 0.9;
}

.shop-now {
  background: #000000;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 25px;
  font-size: 0.9rem;
  font-weight: 600;
}

.category-details {
  padding: 1.5rem;
}

.category-details h4 {
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
  color: #000000;
}

.category-description {
  color: #666666;
  margin-bottom: 1rem;
  line-height: 1.5;
}

.category-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.9rem;
}

.price-range {
  color: #000000;
  font-weight: 600;
}

.item-count {
  color: #888888;
}

@media (max-width: 768px) {
  .categories-grid {
    grid-template-columns: 1fr;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
  
  .category-image {
    height: 200px;
  }
}
</style>
