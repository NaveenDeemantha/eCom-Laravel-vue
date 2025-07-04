<template>
  <section class="contact-form-section">
    <div class="container">
      <div class="section-header">
        <h2>Send Us a Message</h2>
        <p>Fill out the form below and we'll get back to you as soon as possible.</p>
      </div>
      
      <div class="contact-wrapper">
        <div class="form-container">
          <form @submit.prevent="submitForm" class="contact-form">
            <div class="form-group">
              <label for="name">Full Name *</label>
              <input 
                type="text" 
                id="name" 
                v-model="form.name" 
                required 
                :class="{ 'error': errors.name }"
              />
              <span v-if="errors.name" class="error-message">{{ errors.name }}</span>
            </div>
            
            <div class="form-group">
              <label for="email">Email Address *</label>
              <input 
                type="email" 
                id="email" 
                v-model="form.email" 
                required 
                :class="{ 'error': errors.email }"
              />
              <span v-if="errors.email" class="error-message">{{ errors.email }}</span>
            </div>
            
            <div class="form-group">
              <label for="phone">Phone Number</label>
              <input 
                type="tel" 
                id="phone" 
                v-model="form.phone"
              />
            </div>
            
            <div class="form-group">
              <label for="subject">Subject *</label>
              <select 
                id="subject" 
                v-model="form.subject" 
                required 
                :class="{ 'error': errors.subject }"
              >
                <option value="">Select a subject</option>
                <option value="general">General Inquiry</option>
                <option value="support">Technical Support</option>
                <option value="billing">Billing Question</option>
                <option value="feedback">Feedback</option>
                <option value="partnership">Partnership</option>
              </select>
              <span v-if="errors.subject" class="error-message">{{ errors.subject }}</span>
            </div>
            
            <div class="form-group">
              <label for="message">Message *</label>
              <textarea 
                id="message" 
                v-model="form.message" 
                rows="5" 
                required 
                :class="{ 'error': errors.message }"
                placeholder="Tell us how we can help you..."
              ></textarea>
              <span v-if="errors.message" class="error-message">{{ errors.message }}</span>
            </div>
            
            <div class="form-group checkbox-group">
              <label class="checkbox-label">
                <input 
                  type="checkbox" 
                  v-model="form.newsletter"
                />
                <span class="checkmark"></span>
                Subscribe to our newsletter for updates and special offers
              </label>
            </div>
            
            <button 
              type="submit" 
              class="submit-btn" 
              :disabled="isSubmitting"
            >
              <span v-if="isSubmitting">Sending...</span>
              <span v-else>Send Message</span>
            </button>
          </form>
          
          <div v-if="showSuccess" class="success-message">
            <div class="success-icon">✓</div>
            <h3>Message Sent Successfully!</h3>
            <p>Thank you for contacting us. We'll get back to you within 24 hours.</p>
          </div>
        </div>
        
        <div class="contact-info">
          <h3>Get in Touch</h3>
          <div class="info-item">
            <div class="info-icon">📍</div>
            <div>
              <h4>Address</h4>
              <p>123 Fashion Street<br>New York, NY 10001</p>
            </div>
          </div>
          
          <div class="info-item">
            <div class="info-icon">📞</div>
            <div>
              <h4>Phone</h4>
              <p>+1 (555) 123-4567</p>
            </div>
          </div>
          
          <div class="info-item">
            <div class="info-icon">📧</div>
            <div>
              <h4>Email</h4>
              <p>hello@hoomans.com</p>
            </div>
          </div>
          
          <div class="info-item">
            <div class="info-icon">🕒</div>
            <div>
              <h4>Business Hours</h4>
              <p>Mon - Fri: 9:00 AM - 6:00 PM<br>Sat - Sun: 10:00 AM - 4:00 PM</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ContactForm',
  data() {
    return {
      form: {
        name: '',
        email: '',
        phone: '',
        subject: '',
        message: '',
        newsletter: false
      },
      errors: {},
      isSubmitting: false,
      showSuccess: false
    }
  },
  methods: {
    validateForm() {
      this.errors = {};
      
      if (!this.form.name.trim()) {
        this.errors.name = 'Name is required';
      }
      
      if (!this.form.email.trim()) {
        this.errors.email = 'Email is required';
      } else if (!this.isValidEmail(this.form.email)) {
        this.errors.email = 'Please enter a valid email';
      }
      
      if (!this.form.subject) {
        this.errors.subject = 'Please select a subject';
      }
      
      if (!this.form.message.trim()) {
        this.errors.message = 'Message is required';
      }
      
      return Object.keys(this.errors).length === 0;
    },
    
    isValidEmail(email) {
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      return emailRegex.test(email);
    },
    
    async submitForm() {
      if (!this.validateForm()) {
        return;
      }
      
      this.isSubmitting = true;
      
      try {
        // Simulate API call
        await new Promise(resolve => setTimeout(resolve, 2000));
        
        // Reset form
        this.form = {
          name: '',
          email: '',
          phone: '',
          subject: '',
          message: '',
          newsletter: false
        };
        
        this.showSuccess = true;
        
        // Hide success message after 5 seconds
        setTimeout(() => {
          this.showSuccess = false;
        }, 5000);
        
      } catch (error) {
        console.error('Error submitting form:', error);
      } finally {
        this.isSubmitting = false;
      }
    }
  }
}
</script>

<style scoped>
.contact-form-section {
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

.contact-wrapper {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  align-items: start;
}

.form-container {
  background: white;
  padding: 2.5rem;
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  position: relative;
}

.contact-form {
  display: grid;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
}

.form-group label {
  margin-bottom: 0.5rem;
  font-weight: 600;
  color: #000000;
}

.form-group input,
.form-group select,
.form-group textarea {
  padding: 0.75rem;
  border: 2px solid #e1e5e9;
  border-radius: 8px;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #000000;
}

.form-group input.error,
.form-group select.error,
.form-group textarea.error {
  border-color: #dc3545;
}

.error-message {
  color: #dc3545;
  font-size: 0.875rem;
  margin-top: 0.25rem;
}

.checkbox-group {
  flex-direction: row;
  align-items: center;
}

.checkbox-label {
  display: flex;
  align-items: center;
  cursor: pointer;
  font-size: 0.9rem;
  color: #666;
}

.checkbox-label input[type="checkbox"] {
  margin-right: 0.5rem;
}

.submit-btn {
  background: #000000;
  color: white;
  padding: 1rem 2rem;
  border: none;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: 1rem;
}

.submit-btn:hover:not(:disabled) {
  background: #333333;
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.success-message {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  border-radius: 15px;
}

.success-icon {
  width: 60px;
  height: 60px;
  background: #28a745;
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  margin-bottom: 1rem;
}

.success-message h3 {
  color: #28a745;
  margin-bottom: 0.5rem;
}

.success-message p {
  color: #666;
}

.contact-info {
  background: white;
  padding: 2.5rem;
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  height: fit-content;
}

.contact-info h3 {
  margin-bottom: 2rem;
  color: #000000;
  font-size: 1.5rem;
}

.info-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 2rem;
  gap: 1rem;
}

.info-icon {
  font-size: 1.5rem;
  width: 40px;
  height: 40px;
  background: #f8f9fa;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.info-item h4 {
  margin-bottom: 0.5rem;
  color: #000000;
}

.info-item p {
  color: #666666;
  line-height: 1.5;
}

@media (max-width: 768px) {
  .contact-wrapper {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .form-container,
  .contact-info {
    padding: 1.5rem;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
}
</style>
