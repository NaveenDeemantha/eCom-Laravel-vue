<template>
  <section class="faq-section">
    <div class="container">
      <div class="section-header">
        <h2>Frequently Asked Questions</h2>
        <p>Find answers to common questions about our products and services.</p>
      </div>
      
      <div class="faq-grid">
        <div class="faq-item" v-for="(faq, index) in faqs" :key="index">
          <div class="faq-question" @click="toggleFaq(index)">
            <h3>{{ faq.question }}</h3>
            <span class="faq-toggle" :class="{ 'active': faq.isOpen }">+</span>
          </div>
          <div class="faq-answer" :class="{ 'active': faq.isOpen }">
            <p>{{ faq.answer }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FaqSection',
  data() {
    return {
      faqs: [
        {
          question: 'What are your shipping options?',
          answer: 'We offer standard shipping (5-7 business days) and express shipping (2-3 business days). Free shipping is available on orders over $50.',
          isOpen: false
        },
        {
          question: 'What is your return policy?',
          answer: 'We accept returns within 30 days of purchase. Items must be in original condition with tags attached. Return shipping is free for exchanges.',
          isOpen: false
        },
        {
          question: 'How can I track my order?',
          answer: 'Once your order ships, you\'ll receive a tracking number via email. You can also track your order by logging into your account on our website.',
          isOpen: false
        },
        {
          question: 'Do you ship internationally?',
          answer: 'Yes, we ship to over 50 countries worldwide. International shipping rates and delivery times vary by location.',
          isOpen: false
        },
        {
          question: 'What payment methods do you accept?',
          answer: 'We accept all major credit cards, PayPal, Apple Pay, and Google Pay. We also offer buy now, pay later options through Klarna.',
          isOpen: false
        },
        {
          question: 'How do I know what size to order?',
          answer: 'Each product page includes a detailed size chart. You can also contact our customer service team for personalized sizing recommendations.',
          isOpen: false
        },
        {
          question: 'Can I cancel or modify my order?',
          answer: 'You can cancel or modify your order within 1 hour of placing it. After that, please contact our customer service team for assistance.',
          isOpen: false
        },
        {
          question: 'Do you offer student discounts?',
          answer: 'Yes! We offer a 10% student discount. Verify your student status through our partner SheerID to receive your discount code.',
          isOpen: false
        }
      ]
    }
  },
  methods: {
    toggleFaq(index) {
      this.faqs[index].isOpen = !this.faqs[index].isOpen;
    }
  }
}
</script>

<style scoped>
.faq-section {
  padding: 5rem 0;
  background: white;
}

.container {
  max-width: 1000px;
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

.faq-grid {
  display: grid;
  gap: 1rem;
}

.faq-item {
  background: #f8f9fa;
  border-radius: 10px;
  overflow: hidden;
  transition: all 0.3s ease;
}

.faq-item:hover {
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.faq-question {
  padding: 1.5rem;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: white;
  border-bottom: 1px solid #e9ecef;
}

.faq-question h3 {
  margin: 0;
  color: #000000;
  font-size: 1.1rem;
  font-weight: 600;
}

.faq-toggle {
  width: 30px;
  height: 30px;
  background: #000000;
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  transition: all 0.3s ease;
  flex-shrink: 0;
}

.faq-toggle.active {
  transform: rotate(45deg);
  background: #333333;
}

.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: all 0.3s ease;
  background: white;
}

.faq-answer.active {
  max-height: 200px;
}

.faq-answer p {
  padding: 1.5rem;
  margin: 0;
  color: #666666;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .faq-question {
    padding: 1rem;
  }
  
  .faq-question h3 {
    font-size: 1rem;
  }
  
  .faq-answer p {
    padding: 1rem;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
}
</style>
