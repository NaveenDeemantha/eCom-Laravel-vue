<template>
  <section class="newsletter-section">
    <div class="container">
      <div class="newsletter-content">
        <div class="newsletter-text">
          <h2>Stay Updated</h2>
          <p>Subscribe to our newsletter and be the first to know about new products, exclusive deals, and fashion trends.</p>
          <div class="newsletter-benefits">
            <div class="benefit-item">
              <span class="benefit-icon">🎁</span>
              <span>Exclusive offers</span>
            </div>
            <div class="benefit-item">
              <span class="benefit-icon">👕</span>
              <span>New arrivals</span>
            </div>
            <div class="benefit-item">
              <span class="benefit-icon">💡</span>
              <span>Style tips</span>
            </div>
          </div>
        </div>
        
        <div class="newsletter-form">
          <form @submit.prevent="subscribe" class="subscription-form">
            <div class="form-group">
              <input 
                type="email" 
                v-model="email" 
                placeholder="Enter your email address"
                required
                :disabled="isSubmitting"
              />
              <button 
                type="submit" 
                :disabled="isSubmitting"
                class="subscribe-btn"
              >
                <span v-if="isSubmitting">Subscribing...</span>
                <span v-else>Subscribe</span>
              </button>
            </div>
            <div class="privacy-note">
              <small>
                By subscribing, you agree to our 
                <a href="#" @click.prevent>Privacy Policy</a>. 
                You can unsubscribe at any time.
              </small>
            </div>
          </form>
          
          <div v-if="showSuccess" class="success-notification">
            <div class="success-icon">✓</div>
            <div class="success-text">
              <h3>Welcome aboard!</h3>
              <p>Thank you for subscribing. Check your email for a welcome message.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'NewsletterSection',
  data() {
    return {
      email: '',
      isSubmitting: false,
      showSuccess: false
    }
  },
  methods: {
    async subscribe() {
      if (!this.email.trim()) return;
      
      this.isSubmitting = true;
      
      try {
        // Simulate API call
        await new Promise(resolve => setTimeout(resolve, 1500));
        
        // Reset form
        this.email = '';
        this.showSuccess = true;
        
        // Hide success message after 5 seconds
        setTimeout(() => {
          this.showSuccess = false;
        }, 5000);
        
      } catch (error) {
        console.error('Error subscribing:', error);
      } finally {
        this.isSubmitting = false;
      }
    }
  }
}
</script>

<style scoped>
.newsletter-section {
  padding: 5rem 0;
  background: linear-gradient(135deg, #000000 0%, #333333 100%);
  color: white;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.newsletter-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.newsletter-text h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  font-weight: bold;
}

.newsletter-text p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  opacity: 0.9;
  line-height: 1.6;
}

.newsletter-benefits {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.benefit-item {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-size: 1.1rem;
}

.benefit-icon {
  font-size: 1.5rem;
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  backdrop-filter: blur(10px);
}

.newsletter-form {
  background: rgba(255, 255, 255, 0.1);
  padding: 2rem;
  border-radius: 15px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  position: relative;
}

.subscription-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.form-group {
  display: flex;
  gap: 0.5rem;
}

.form-group input {
  flex: 1;
  padding: 0.75rem 1rem;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  background: white;
  color: #333;
}

.form-group input:focus {
  outline: none;
  box-shadow: 0 0 0 2px rgba(255, 255, 255, 0.5);
}

.form-group input:disabled {
  opacity: 0.7;
}

.subscribe-btn {
  padding: 0.75rem 1.5rem;
  background: #ffffff;
  color: #000000;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  white-space: nowrap;
}

.subscribe-btn:hover:not(:disabled) {
  background: #f0f0f0;
  color: #000000;
  transform: translateY(-2px);
}

.subscribe-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.privacy-note {
  text-align: center;
  opacity: 0.8;
}

.privacy-note a {
  color: white;
  text-decoration: underline;
}

.success-notification {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(255, 255, 255, 0.95);
  color: #333;
  border-radius: 15px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  padding: 2rem;
}

.success-icon {
  width: 50px;
  height: 50px;
  background: #28a745;
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  flex-shrink: 0;
}

.success-text h3 {
  margin: 0 0 0.5rem 0;
  color: #28a745;
}

.success-text p {
  margin: 0;
  color: #666666;
}

@media (max-width: 768px) {
  .newsletter-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }
  
  .newsletter-text h2 {
    font-size: 2rem;
  }
  
  .form-group {
    flex-direction: column;
  }
  
  .newsletter-form {
    padding: 1.5rem;
  }
  
  .success-notification {
    flex-direction: column;
    text-align: center;
  }
}
</style>
