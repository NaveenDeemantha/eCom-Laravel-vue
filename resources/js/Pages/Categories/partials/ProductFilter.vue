<template>
  <section id="products-section" class="products-section">
    <div class="container">
      <div class="section-header">
        <h2>Featured Products</h2>
        <p>Discover our handpicked selection of trending items</p>
      </div>
      
      <div class="products-layout">
        <!-- Filter Sidebar -->
        <div class="filter-sidebar">
          <div class="filter-header">
            <h3>Filter Products</h3>
            <button class="clear-filters" @click="clearFilters">Clear All</button>
          </div>
          
          <!-- Category Filter -->
          <div class="filter-group">
            <h4>Category</h4>
            <div class="filter-options">
              <label v-for="category in categories" :key="category" class="filter-option">
                <input 
                  type="checkbox" 
                  :value="category" 
                  v-model="selectedCategories"
                  @change="applyFilters"
                />
                <span class="checkmark"></span>
                {{ category }}
              </label>
            </div>
          </div>
          
          <!-- Price Range Filter -->
          <div class="filter-group">
            <h4>Price Range</h4>
            <div class="price-range">
              <input 
                type="range" 
                :min="priceRange.min" 
                :max="priceRange.max" 
                v-model="selectedPriceRange"
                @input="applyFilters"
                class="price-slider"
              />
              <div class="price-labels">
                <span>${{ priceRange.min }}</span>
                <span>${{ selectedPriceRange }}</span>
              </div>
            </div>
          </div>
          
          <!-- Size Filter -->
          <div class="filter-group">
            <h4>Size</h4>
            <div class="size-options">
              <button 
                v-for="size in sizes" 
                :key="size"
                class="size-button"
                :class="{ 'active': selectedSizes.includes(size) }"
                @click="toggleSize(size)"
              >
                {{ size }}
              </button>
            </div>
          </div>
          
          <!-- Color Filter -->
          <div class="filter-group">
            <h4>Color</h4>
            <div class="color-options">
              <button 
                v-for="color in colors" 
                :key="color.name"
                class="color-button"
                :class="{ 'active': selectedColors.includes(color.name) }"
                :style="{ backgroundColor: color.hex }"
                @click="toggleColor(color.name)"
                :title="color.name"
              ></button>
            </div>
          </div>
        </div>
        
        <!-- Products Grid -->
        <div class="products-grid">
          <div class="products-toolbar">
            <div class="results-count">
              Showing {{ filteredProducts.length }} of {{ products.length }} products
            </div>
            <div class="sort-options">
              <select v-model="sortBy" @change="applyFilters" class="sort-select">
                <option value="name">Sort by Name</option>
                <option value="price-low">Price: Low to High</option>
                <option value="price-high">Price: High to Low</option>
                <option value="newest">Newest First</option>
                <option value="rating">Best Rating</option>
              </select>
            </div>
          </div>
          
          <div class="products-list">
            <div 
              v-for="product in filteredProducts" 
              :key="product.id" 
              class="product-card"
            >
              <div class="product-image">
                <img :src="product.image" :alt="product.name" />
                <div class="product-actions">
                  <button class="quick-view" @click="quickView(product)">Quick View</button>
                  <button class="add-to-wishlist" @click="addToWishlist(product)">♡</button>
                </div>
                <div v-if="product.isNew" class="product-badge new">New</div>
                <div v-if="product.discount" class="product-badge sale">-{{ product.discount }}%</div>
              </div>
              
              <div class="product-info">
                <h3 class="product-name">{{ product.name }}</h3>
                <p class="product-category">{{ product.category }}</p>
                <div class="product-rating">
                  <span class="stars">★★★★☆</span>
                  <span class="rating-count">({{ product.reviews }})</span>
                </div>
                <div class="product-price">
                  <span v-if="product.originalPrice" class="original-price">${{ product.originalPrice }}</span>
                  <span class="current-price">${{ product.price }}</span>
                </div>
                <div class="product-sizes">
                  <span v-for="size in product.sizes" :key="size" class="size-tag">{{ size }}</span>
                </div>
                <button class="add-to-cart" @click="addToCart(product)">Add to Cart</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProductFilter',
  data() {
    return {
      products: [
        {
          id: 1,
          name: "Premium Cotton T-Shirt",
          category: "Men's Clothing",
          price: 29.99,
          originalPrice: 39.99,
          image: "/images/tshirt0.jpg",
          sizes: ["S", "M", "L", "XL"],
          colors: ["Black", "White", "Blue"],
          reviews: 124,
          isNew: true,
          discount: 25
        },
        {
          id: 2,
          name: "Summer Floral Dress",
          category: "Women's Fashion",
          price: 79.99,
          image: "/images/imgs3.webp",
          sizes: ["XS", "S", "M", "L"],
          colors: ["Red", "Pink", "Blue"],
          reviews: 89,
          isNew: false
        },
        {
          id: 3,
          name: "Kids Adventure Hoodie",
          category: "Kids' Wear",
          price: 34.99,
          image: "/images/imgs4.webp",
          sizes: ["2T", "3T", "4T", "5T"],
          colors: ["Green", "Blue", "Orange"],
          reviews: 156,
          isNew: true
        },
        {
          id: 4,
          name: "Athletic Running Shorts",
          category: "Activewear",
          price: 24.99,
          originalPrice: 34.99,
          image: "/images/imgs5.webp",
          sizes: ["S", "M", "L", "XL"],
          colors: ["Black", "Blue", "Red"],
          reviews: 203,
          discount: 30
        },
        {
          id: 5,
          name: "Leather Crossbody Bag",
          category: "Accessories",
          price: 89.99,
          image: "/images/imgs6.webp",
          sizes: ["One Size"],
          colors: ["Brown", "Black", "Tan"],
          reviews: 67,
          isNew: false
        },
        {
          id: 6,
          name: "Classic Sneakers",
          category: "Footwear",
          price: 129.99,
          image: "/images/imgs7.webp",
          sizes: ["7", "8", "9", "10", "11"],
          colors: ["White", "Black", "Gray"],
          reviews: 298,
          isNew: true
        }
      ],
      categories: ["Men's Clothing", "Women's Fashion", "Kids' Wear", "Activewear", "Accessories", "Footwear"],
      sizes: ["XS", "S", "M", "L", "XL", "2T", "3T", "4T", "5T", "7", "8", "9", "10", "11"],
      colors: [
        { name: "Black", hex: "#000000" },
        { name: "White", hex: "#FFFFFF" },
        { name: "Blue", hex: "#3498db" },
        { name: "Red", hex: "#e74c3c" },
        { name: "Green", hex: "#2ecc71" },
        { name: "Pink", hex: "#f39c12" },
        { name: "Brown", hex: "#8b4513" },
        { name: "Gray", hex: "#95a5a6" },
        { name: "Orange", hex: "#f39c12" },
        { name: "Tan", hex: "#d2691e" }
      ],
      selectedCategories: [],
      selectedSizes: [],
      selectedColors: [],
      selectedPriceRange: 200,
      priceRange: { min: 0, max: 200 },
      sortBy: 'name',
      filteredProducts: []
    }
  },
  mounted() {
    this.filteredProducts = this.products;
  },
  methods: {
    applyFilters() {
      let filtered = [...this.products];
      
      // Category filter
      if (this.selectedCategories.length > 0) {
        filtered = filtered.filter(product => 
          this.selectedCategories.includes(product.category)
        );
      }
      
      // Price filter
      filtered = filtered.filter(product => product.price <= this.selectedPriceRange);
      
      // Size filter
      if (this.selectedSizes.length > 0) {
        filtered = filtered.filter(product => 
          product.sizes.some(size => this.selectedSizes.includes(size))
        );
      }
      
      // Color filter
      if (this.selectedColors.length > 0) {
        filtered = filtered.filter(product => 
          product.colors.some(color => this.selectedColors.includes(color))
        );
      }
      
      // Sort
      switch (this.sortBy) {
        case 'price-low':
          filtered.sort((a, b) => a.price - b.price);
          break;
        case 'price-high':
          filtered.sort((a, b) => b.price - a.price);
          break;
        case 'newest':
          filtered.sort((a, b) => b.isNew - a.isNew);
          break;
        case 'rating':
          filtered.sort((a, b) => b.reviews - a.reviews);
          break;
        default:
          filtered.sort((a, b) => a.name.localeCompare(b.name));
      }
      
      this.filteredProducts = filtered;
    },
    
    clearFilters() {
      this.selectedCategories = [];
      this.selectedSizes = [];
      this.selectedColors = [];
      this.selectedPriceRange = 200;
      this.sortBy = 'name';
      this.filteredProducts = this.products;
    },
    
    toggleSize(size) {
      const index = this.selectedSizes.indexOf(size);
      if (index > -1) {
        this.selectedSizes.splice(index, 1);
      } else {
        this.selectedSizes.push(size);
      }
      this.applyFilters();
    },
    
    toggleColor(color) {
      const index = this.selectedColors.indexOf(color);
      if (index > -1) {
        this.selectedColors.splice(index, 1);
      } else {
        this.selectedColors.push(color);
      }
      this.applyFilters();
    },
    
    quickView(product) {
      // Implement quick view functionality
      console.log('Quick view:', product);
    },
    
    addToWishlist(product) {
      // Implement wishlist functionality
      console.log('Added to wishlist:', product);
    },
    
    addToCart(product) {
      // Implement add to cart functionality
      console.log('Added to cart:', product);
    }
  }
}
</script>

<style scoped>
.products-section {
  padding: 5rem 0;
  background: white;
}

.container {
  max-width: 1400px;
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

.products-layout {
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 3rem;
}

.filter-sidebar {
  background: #f8f9fa;
  padding: 2rem;
  border-radius: 15px;
  height: fit-content;
  position: sticky;
  top: 140px;
}

.filter-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
}

.filter-header h3 {
  margin: 0;
  color: #000000;
}

.clear-filters {
  background: none;
  border: none;
  color: #000000;
  cursor: pointer;
  font-size: 0.9rem;
}

.filter-group {
  margin-bottom: 2rem;
}

.filter-group h4 {
  margin-bottom: 1rem;
  color: #000000;
  font-size: 1.1rem;
}

.filter-options {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.filter-option {
  display: flex;
  align-items: center;
  cursor: pointer;
  font-size: 0.9rem;
}

.filter-option input[type="checkbox"] {
  margin-right: 0.5rem;
}

.price-range {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.price-slider {
  width: 100%;
  height: 5px;
  background: #ddd;
  border-radius: 5px;
  outline: none;
}

.price-labels {
  display: flex;
  justify-content: space-between;
  font-size: 0.9rem;
  color: #666;
}

.size-options {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.size-button {
  padding: 0.5rem 1rem;
  border: 1px solid #ddd;
  background: white;
  cursor: pointer;
  border-radius: 5px;
  font-size: 0.9rem;
}

.size-button.active {
  background: #000000;
  color: white;
  border-color: #000000;
}

.color-options {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.color-button {
  width: 30px;
  height: 30px;
  border: 2px solid #ddd;
  border-radius: 50%;
  cursor: pointer;
  transition: all 0.3s ease;
}

.color-button.active {
  border-color: #000000;
  transform: scale(1.1);
}

.products-grid {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.products-toolbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
  border-bottom: 1px solid #eee;
}

.results-count {
  color: #666666;
  font-size: 0.9rem;
}

.sort-select {
  padding: 0.5rem 1rem;
  border: 1px solid #ddd;
  border-radius: 5px;
  background: white;
}

.products-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 2rem;
}

.product-card {
  background: white;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.product-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
}

.product-image {
  position: relative;
  height: 250px;
  overflow: hidden;
}

.product-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.product-card:hover .product-image img {
  transform: scale(1.05);
}

.product-actions {
  position: absolute;
  top: 1rem;
  right: 1rem;
  display: flex;
  gap: 0.5rem;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.product-card:hover .product-actions {
  opacity: 1;
}

.quick-view,
.add-to-wishlist {
  background: white;
  border: none;
  padding: 0.5rem;
  border-radius: 50%;
  cursor: pointer;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

.product-badge {
  position: absolute;
  top: 1rem;
  left: 1rem;
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 600;
}

.product-badge.new {
  background: #2ecc71;
  color: white;
}

.product-badge.sale {
  background: #e74c3c;
  color: white;
}

.product-info {
  padding: 1.5rem;
}

.product-name {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
  color: #000000;
}

.product-category {
  color: #666666;
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}

.product-rating {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.stars {
  color: #f39c12;
}

.rating-count {
  color: #666666;
  font-size: 0.9rem;
}

.product-price {
  margin-bottom: 1rem;
}

.original-price {
  text-decoration: line-through;
  color: #888888;
  margin-right: 0.5rem;
}

.current-price {
  font-size: 1.3rem;
  font-weight: bold;
  color: #000000;
}

.product-sizes {
  display: flex;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.size-tag {
  background: #f8f9fa;
  padding: 0.25rem 0.5rem;
  border-radius: 5px;
  font-size: 0.8rem;
}

.add-to-cart {
  width: 100%;
  background: #000000;
  color: white;
  border: none;
  padding: 0.75rem;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  transition: background 0.3s ease;
}

.add-to-cart:hover {
  background: #333333;
}

@media (max-width: 1024px) {
  .products-layout {
    grid-template-columns: 1fr;
  }
  
  .filter-sidebar {
    position: static;
    order: 2;
  }
  
  .products-grid {
    order: 1;
  }
}

@media (max-width: 768px) {
  .products-list {
    grid-template-columns: 1fr;
  }
  
  .products-toolbar {
    flex-direction: column;
    gap: 1rem;
    align-items: stretch;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
}
</style>
