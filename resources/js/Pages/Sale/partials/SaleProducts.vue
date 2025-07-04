<template>
    <section class="sale-products">
        <div class="container">
            <h2 class="section-title">Hot Deals</h2>
            <div class="products-grid">
                <div class="product-card" v-for="product in saleProducts" :key="product.id">
                    <div class="product-image">
                        <img :src="product.image" :alt="product.name" />
                        <div class="discount-badge">{{ product.discount }}% OFF</div>
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">{{ product.name }}</h3>
                        <div class="price-section">
                            <span class="original-price">${{ product.originalPrice }}</span>
                            <span class="sale-price">${{ product.salePrice }}</span>
                        </div>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'SaleProducts',
    data() {
        return {
            saleProducts: [
                {
                    id: 1,
                    name: 'Premium T-Shirt',
                    image: '/images/tshirt0.jpg',
                    originalPrice: 29.99,
                    salePrice: 19.99,
                    discount: 33
                },
                {
                    id: 2,
                    name: 'Casual Hoodie',
                    image: '/images/imgs2.webp',
                    originalPrice: 59.99,
                    salePrice: 39.99,
                    discount: 33
                },
                {
                    id: 3,
                    name: 'Denim Jacket',
                    image: '/images/imgs3.webp',
                    originalPrice: 89.99,
                    salePrice: 54.99,
                    discount: 39
                },
                {
                    id: 4,
                    name: 'Summer Dress',
                    image: '/images/imgs4.webp',
                    originalPrice: 49.99,
                    salePrice: 29.99,
                    discount: 40
                },
                {
                    id: 5,
                    name: 'Sneakers',
                    image: '/images/imgs5.webp',
                    originalPrice: 79.99,
                    salePrice: 49.99,
                    discount: 38
                },
                {
                    id: 6,
                    name: 'Backpack',
                    image: '/images/imgs6.webp',
                    originalPrice: 39.99,
                    salePrice: 24.99,
                    discount: 38
                }
            ]
        }
    }
}
</script>

<style scoped>
.sale-products {
    padding: 4rem 0;
    background: #f8f9fa;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 3rem;
  color: #000000;
}

.products-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
}

.product-card {
    background: white;
    border-radius: 15px;
    overflow: hidden;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.product-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
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

.discount-badge {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: #000000;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 25px;
  font-weight: bold;
  font-size: 0.9rem;
}

.product-info {
  padding: 1.5rem;
}

.product-name {
  font-size: 1.3rem;
  margin-bottom: 1rem;
  color: #000000;
}

.price-section {
    margin-bottom: 1.5rem;
}

.original-price {
  text-decoration: line-through;
  color: #888888;
  margin-right: 1rem;
  font-size: 1.1rem;
}

.sale-price {
  color: #000000;
  font-weight: bold;
  font-size: 1.3rem;
}

.add-to-cart {
  width: 100%;
  background: #000000;
  color: white;
  border: none;
  padding: 0.8rem;
  border-radius: 8px;
  font-size: 1.1rem;
  cursor: pointer;
  transition: background 0.3s ease;
}

.add-to-cart:hover {
  background: #333333;
}

@media (max-width: 768px) {
    .products-grid {
        grid-template-columns: 1fr;
    }
    
    .section-title {
        font-size: 2rem;
    }
}
</style>
