<template>
    <section class="about-section">
        <div class="container-desc">
            <!-- Main Story Section -->
            <div class="story-section">
                <div class="story-content">
                    <div class="section-badge">
                        <span class="badge-text">Our Story</span>
                    </div>
                    <h2 class="story-title">Redefining Digital Commerce</h2>
                    <p class="story-text">
                        Born from a vision to transform how people shop online, we've built more than just an ecommerce platform—we've created a digital ecosystem where innovation meets exceptional customer experience. Our journey began with a simple belief: every customer deserves access to premium products, seamless service, and trustworthy transactions.
                    </p>
                    <div class="story-highlights">
                        <div class="highlight-item">
                            <div class="highlight-icon">🎯</div>
                            <div class="highlight-content">
                                <h4>Customer-First Approach</h4>
                                <p>Every decision we make starts with our customers in mind</p>
                            </div>
                        </div>
                        <div class="highlight-item">
                            <div class="highlight-icon">🚀</div>
                            <div class="highlight-content">
                                <h4>Innovation Driven</h4>
                                <p>Constantly evolving to meet tomorrow's needs today</p>
                            </div>
                        </div>
                        <div class="highlight-item">
                            <div class="highlight-icon">🌱</div>
                            <div class="highlight-content">
                                <h4>Sustainable Future</h4>
                                <p>Building responsible commerce for generations to come</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="story-visual">
                    <div class="visual-card">
                        <img src="/images/imgs3.webp" alt="Our workspace" class="story-image" />
                        <div class="card-overlay">
                            <div class="overlay-content">
                                <h3>Our Workspace</h3>
                                <p>Where innovation happens daily</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Mission & Vision Section -->
            <div class="mission-vision-section">
                <div class="mission-card">
                    <div class="card-header">
                        <div class="card-icon">🎯</div>
                        <h3>Our Mission</h3>
                    </div>
                    <p>To revolutionize online shopping by creating seamless, personalized experiences that connect customers with products they love, while fostering sustainable and ethical business practices that benefit everyone.</p>
                    <div class="mission-points">
                        <div class="point">
                            <span class="point-icon">✓</span>
                            <span>Exceptional customer experience</span>
                        </div>
                        <div class="point">
                            <span class="point-icon">✓</span>
                            <span>Sustainable business practices</span>
                        </div>
                        <div class="point">
                            <span class="point-icon">✓</span>
                            <span>Innovative technology solutions</span>
                        </div>
                    </div>
                </div>
                
                <div class="vision-card">
                    <div class="card-header">
                        <div class="card-icon">🔮</div>
                        <h3>Our Vision</h3>
                    </div>
                    <p>To be the world's most trusted and innovative ecommerce platform, where every interaction creates value, every purchase builds relationships, and every customer becomes a brand advocate.</p>
                    <div class="vision-metrics">
                        <div class="metric">
                            <div class="metric-number">2030</div>
                            <div class="metric-label">Global Leadership</div>
                        </div>
                        <div class="metric">
                            <div class="metric-number">1M+</div>
                            <div class="metric-label">Happy Customers</div>
                        </div>
                        <div class="metric">
                            <div class="metric-number">100%</div>
                            <div class="metric-label">Sustainability</div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Team Section -->
            <div class="team-section">
                <div class="team-header">
                    <h3>Meet Our Leadership Team</h3>
                    <p>The visionaries driving our success</p>
                </div>
                <div class="team-grid">
                    <div class="team-member" v-for="member in teamMembers" :key="member.name">
                        <div class="member-image">
                            <img :src="member.image" :alt="member.name" />
                            <div class="member-overlay">
                                <div class="social-links">
                                    <a href="#" class="social-link">📧</a>
                                    <a href="#" class="social-link">💼</a>
                                </div>
                            </div>
                        </div>
                        <div class="member-info">
                            <h4>{{ member.name }}</h4>
                            <p class="member-role">{{ member.role }}</p>
                            <p class="member-bio">{{ member.bio }}</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Testimonials Section -->
            <div class="testimonials-section">
                <div class="testimonials-header">
                    <h3>What Our Customers Say</h3>
                    <p>Real experiences from real customers</p>
                </div>
                <div class="testimonials-grid">
                    <div class="testimonial-card" v-for="testimonial in testimonials" :key="testimonial.name">
                        <div class="testimonial-content">
                            <div class="quote-icon">"</div>
                            <p>{{ testimonial.text }}</p>
                            <div class="testimonial-rating">
                                <span v-for="i in 5" :key="i" class="star">⭐</span>
                            </div>
                        </div>
                        <div class="testimonial-author">
                            <div class="author-info">
                                <h4>{{ testimonial.name }}</h4>
                                <p>{{ testimonial.location }}</p>
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
    name: 'AboutDescription',
    data() {
        return {
            teamMembers: [
                {
                    name: 'John Doe',
                    role: 'Founder & CEO',
                    bio: 'Visionary leader with 10+ years in e-commerce',
                    image: 'https://randomuser.me/api/portraits/men/32.jpg'
                },
                {
                    name: 'Jane Smith',
                    role: 'Head of Marketing',
                    bio: 'Strategic marketing expert driving growth',
                    image: 'https://randomuser.me/api/portraits/women/44.jpg'
                },
                {
                    name: 'Mike Lee',
                    role: 'Lead Developer',
                    bio: 'Technical architect of our platform',
                    image: 'https://randomuser.me/api/portraits/men/65.jpg'
                },
                {
                    name: 'Sarah Johnson',
                    role: 'Customer Success',
                    bio: 'Ensuring exceptional customer experiences',
                    image: 'https://randomuser.me/api/portraits/women/68.jpg'
                }
            ],
            testimonials: [
                {
                    name: 'Emily Rodriguez',
                    location: 'New York, USA',
                    text: 'Fantastic service and amazing products! Shopping here is always a pleasure. The quality exceeds expectations every time.'
                },
                {
                    name: 'Alex Thompson',
                    location: 'London, UK',
                    text: 'Quick delivery and great support. Highly recommended! The customer service team goes above and beyond.'
                },
                {
                    name: 'Maria Garcia',
                    location: 'Barcelona, Spain',
                    text: 'Love the variety and quality of products. The shopping experience is seamless and enjoyable.'
                }
            ]
        }
    }
}
</script>

<style scoped>
.about-section {
    padding: 5rem 0;
    background: #ffffff;
    color: #333333;
}

.container-desc {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
}

/* Story Section */
.story-section {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
    margin-bottom: 5rem;
}

.story-content {
    text-align: left;
}

.section-badge {
    display: inline-block;
    background: #f8f9fa;
    border: 2px solid #e9ecef;
    border-radius: 50px;
    padding: 0.5rem 1.5rem;
    margin-bottom: 2rem;
}

.badge-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #000000;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.story-title {
    font-size: 3rem;
    font-weight: 800;
    line-height: 1.2;
    margin-bottom: 1.5rem;
    color: #000000;
}

.story-text {
    font-size: 1.1rem;
    line-height: 1.7;
    color: #666666;
    margin-bottom: 2rem;
}

.story-highlights {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}

.highlight-item {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
}

.highlight-icon {
    font-size: 2rem;
    min-width: 60px;
    height: 60px;
    background: #f8f9fa;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px solid #e9ecef;
}

.highlight-content h4 {
    font-size: 1.2rem;
    font-weight: 600;
    color: #000000;
    margin-bottom: 0.5rem;
}

.highlight-content p {
    font-size: 1rem;
    color: #666666;
    line-height: 1.5;
}

.story-visual {
    position: relative;
}

.visual-card {
    position: relative;
    border-radius: 20px;
    overflow: hidden;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease;
}

.visual-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 30px 60px rgba(0, 0, 0, 0.15);
}

.story-image {
    width: 100%;
    height: 400px;
    object-fit: cover;
}

.card-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(transparent, rgba(0, 0, 0, 0.8));
    color: white;
    padding: 2rem;
}

.overlay-content h3 {
    font-size: 1.5rem;
    font-weight: 600;
    margin-bottom: 0.5rem;
}

.overlay-content p {
    font-size: 1rem;
    opacity: 0.9;
}

/* Mission & Vision Section */
.mission-vision-section {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    margin-bottom: 5rem;
}

.mission-card, .vision-card {
    background: #f8f9fa;
    border: 2px solid #e9ecef;
    border-radius: 20px;
    padding: 2.5rem;
    transition: all 0.3s ease;
}

.mission-card:hover, .vision-card:hover {
    transform: translateY(-5px);
    border-color: #000000;
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.card-header {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-bottom: 1.5rem;
}

.card-icon {
    font-size: 2rem;
    width: 60px;
    height: 60px;
    background: #ffffff;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px solid #e9ecef;
}

.card-header h3 {
    font-size: 1.8rem;
    font-weight: 700;
    color: #000000;
}

.mission-card p, .vision-card p {
    font-size: 1.1rem;
    line-height: 1.6;
    color: #666666;
    margin-bottom: 2rem;
}

.mission-points {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.point {
    display: flex;
    align-items: center;
    gap: 0.8rem;
}

.point-icon {
    width: 24px;
    height: 24px;
    background: #000000;
    color: white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.8rem;
    font-weight: bold;
}

.vision-metrics {
    display: flex;
    justify-content: space-between;
    gap: 1rem;
}

.metric {
    text-align: center;
}

.metric-number {
    font-size: 1.8rem;
    font-weight: bold;
    color: #000000;
    margin-bottom: 0.5rem;
}

.metric-label {
    font-size: 0.9rem;
    color: #666666;
    text-transform: uppercase;
    letter-spacing: 1px;
}

/* Team Section */
.team-section {
    margin-bottom: 5rem;
}

.team-header {
    text-align: center;
    margin-bottom: 3rem;
}

.team-header h3 {
    font-size: 2.5rem;
    font-weight: 700;
    color: #000000;
    margin-bottom: 1rem;
}

.team-header p {
    font-size: 1.2rem;
    color: #666666;
}

.team-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
}

.team-member {
    background: #f8f9fa;
    border: 2px solid #e9ecef;
    border-radius: 20px;
    padding: 2rem;
    text-align: center;
    transition: all 0.3s ease;
}

.team-member:hover {
    transform: translateY(-5px);
    border-color: #000000;
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.member-image {
    position: relative;
    margin-bottom: 1.5rem;
}

.member-image img {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    object-fit: cover;
    border: 4px solid #ffffff;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.member-overlay {
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 100px;
    height: 100px;
    background: rgba(0, 0, 0, 0.8);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.team-member:hover .member-overlay {
    opacity: 1;
}

.social-links {
    display: flex;
    gap: 0.5rem;
}

.social-link {
    width: 30px;
    height: 30px;
    background: rgba(255, 255, 255, 0.2);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    text-decoration: none;
    font-size: 0.9rem;
    transition: all 0.3s ease;
}

.social-link:hover {
    background: rgba(255, 255, 255, 0.3);
    transform: scale(1.1);
}

.member-info h4 {
    font-size: 1.3rem;
    font-weight: 600;
    color: #000000;
    margin-bottom: 0.5rem;
}

.member-role {
    font-size: 1rem;
    color: #666666;
    font-weight: 500;
    margin-bottom: 1rem;
}

.member-bio {
    font-size: 0.9rem;
    color: #666666;
    line-height: 1.5;
}

/* Testimonials Section */
.testimonials-section {
    margin-bottom: 2rem;
}

.testimonials-header {
    text-align: center;
    margin-bottom: 3rem;
}

.testimonials-header h3 {
    font-size: 2.5rem;
    font-weight: 700;
    color: #000000;
    margin-bottom: 1rem;
}

.testimonials-header p {
    font-size: 1.2rem;
    color: #666666;
}

.testimonials-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
}

.testimonial-card {
    background: #f8f9fa;
    border: 2px solid #e9ecef;
    border-radius: 20px;
    padding: 2rem;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
}

.testimonial-card::before {
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

.testimonial-card:hover {
    transform: translateY(-5px);
    border-color: #000000;
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}

.testimonial-card:hover::before {
    opacity: 1;
}

.testimonial-content {
    position: relative;
    z-index: 1;
    margin-bottom: 1.5rem;
}

.quote-icon {
    font-size: 3rem;
    color: #e9ecef;
    line-height: 1;
    margin-bottom: 1rem;
}

.testimonial-content p {
    font-size: 1.1rem;
    line-height: 1.6;
    color: #333333;
    margin-bottom: 1rem;
}

.testimonial-rating {
    margin-bottom: 1rem;
}

.star {
    font-size: 1rem;
    margin-right: 0.2rem;
}

.testimonial-author {
    position: relative;
    z-index: 1;
}

.author-info h4 {
    font-size: 1.1rem;
    font-weight: 600;
    color: #000000;
    margin-bottom: 0.3rem;
}

.author-info p {
    font-size: 0.9rem;
    color: #666666;
}

/* Responsive Design */
@media (max-width: 768px) {
    .story-section {
        grid-template-columns: 1fr;
        gap: 2rem;
    }
    
    .story-visual {
        order: -1;
    }
    
    .mission-vision-section {
        grid-template-columns: 1fr;
        gap: 2rem;
    }
    
    .team-grid {
        grid-template-columns: 1fr;
    }
    
    .testimonials-grid {
        grid-template-columns: 1fr;
    }
    
    .story-title {
        font-size: 2.5rem;
    }
    
    .team-header h3,
    .testimonials-header h3 {
        font-size: 2rem;
    }
    
    .vision-metrics {
        flex-direction: column;
        gap: 1rem;
    }
}
</style>