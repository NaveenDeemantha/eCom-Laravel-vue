<template>
    <section class="sale-hero">
        <div class="container">
            <h1 class="hero-title">🔥 MEGA SALE 🔥</h1>
            <p class="hero-subtitle">
                Up to 70% off on selected items! Don't miss out on these incredible deals.
            </p>
            <div class="sale-stats">
                <div class="stat-item">
                    <span class="stat-number">70%</span>
                    <span class="stat-label">Max Discount</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">500+</span>
                    <span class="stat-label">Items on Sale</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">48h</span>
                    <span class="stat-label">Time Left</span>
                </div>
            </div>
            <button class="cta-button">Shop Now</button>
        </div>
    </section>
</template>

<script>
export default {
    name: 'SaleHero'
}
</script>

<style scoped>
.sale-hero {
  background: linear-gradient(135deg, #000000, #333333);
  color: white;
  padding: 4rem 0;
  text-align: center;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
}

.hero-title {
    font-size: 3.5rem;
    margin-bottom: 1rem;
    font-weight: bold;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.hero-subtitle {
    font-size: 1.5rem;
    margin-bottom: 3rem;
    opacity: 0.9;
}

.sale-stats {
    display: flex;
    justify-content: center;
    gap: 3rem;
    margin-bottom: 3rem;
}

.stat-item {
    text-align: center;
}

.stat-number {
    display: block;
    font-size: 2.5rem;
    font-weight: bold;
    color: #fff;
}

.stat-label {
    font-size: 1rem;
    opacity: 0.8;
}

.cta-button {
  background: white;
  color: #000000;
  padding: 1rem 2rem;
  border: none;
  border-radius: 50px;
  font-size: 1.2rem;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

.cta-button:hover {
  background: #f0f0f0;
  color: #000000;
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
}

@media (max-width: 768px) {
    .hero-title {
        font-size: 2.5rem;
    }
    
    .sale-stats {
        flex-direction: column;
        gap: 1.5rem;
    }
    
    .stat-number {
        font-size: 2rem;
    }
}
</style>
