<template>
    <section class="about-section">
        <div class="container-desc">
            <h2 class="about-title">About Our Store</h2>
            <p class="about-text">
                Welcome to our ecommerce platform, your one-stop destination for the latest trends in fashion, electronics, and lifestyle products. We are committed to providing a seamless shopping experience, offering a curated selection of high-quality items at competitive prices. Our mission is to empower customers with choice, convenience, and confidence in every purchase.
            </p>
            <ul class="about-features">
                <li>✔️ Wide range of products from top brands</li>
                <li>✔️ Fast and reliable shipping</li>
                <li>✔️ Secure payment options</li>
                <li>✔️ 24/7 customer support</li>
                <li>✔️ Easy returns and exchanges</li>
            </ul>
        </div>
        <div class="about-extra">
            <section class="about-mission">
                <h3>Our Mission</h3>
                <p>
                    To revolutionize online shopping by making it more accessible, enjoyable, and trustworthy for everyone. We strive to connect people with products they love, while supporting sustainable and ethical business practices.
                </p>
            </section>
            <section class="about-team">
                <h3>Meet the Team</h3>
                <div class="team-list">
                    <div class="team-member">
                        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="John Doe" />
                        <span>John Doe<br/><small>Founder & CEO</small></span>
                    </div>
                    <div class="team-member">
                        <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="Jane Smith" />
                        <span>Jane Smith<br/><small>Head of Marketing</small></span>
                    </div>
                    <div class="team-member">
                        <img src="https://randomuser.me/api/portraits/men/65.jpg" alt="Mike Lee" />
                        <span>Mike Lee<br/><small>Lead Developer</small></span>
                    </div>
                </div>
            </section>
            <section class="about-testimonials">
                <h3>Customer Testimonials</h3>
                <blockquote>
                    "Fantastic service and amazing products! Shopping here is always a pleasure."
                    <footer>- Emily R.</footer>
                </blockquote>
                <blockquote>
                    "Quick delivery and great support. Highly recommended!"
                    <footer>- Alex T.</footer>
                </blockquote>
            </section>
        </div>
    </section>
</template>

<style scoped>
.about-section {
    background: #f9fafb;
    padding: 3rem 1rem;
}

.container-desc {
    max-width: 720px;
    margin: 0 auto;
    background: #ffffff;
    border-radius: 1rem;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.05);
    padding: 2.5rem 2rem;
    text-align: center;
}

.about-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: #0a0a0a;
    margin-bottom: 1rem;
    letter-spacing: 0.5px;
}

.about-text {
    font-size: 1.1rem;
    color: #333333;
    margin-bottom: 1.5rem;
    line-height: 1.8;
}

.about-features {
    list-style: none;
    padding: 0;
    margin: 0;
}

.about-features li {
    font-size: 1rem;
    color: #222222;
    margin-bottom: 0.75rem;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    text-align: left;
}

.about-extra {
    margin-top: 3rem;
    display: flex;
    flex-direction: column;
    gap: 2.5rem;
}

.about-mission,
.about-team,
.about-testimonials {
    background: #f0f2f5;
    border-left: 6px solid #0d1f3c;
    border-radius: 0.75rem;
    padding: 1.8rem 1.5rem;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.03);
}

.about-mission h3,
.about-team h3,
.about-testimonials h3 {
    font-size: 1.5rem;
    color: #0d1f3c;
    margin-bottom: 0.8rem;
    font-weight: 600;
    text-align: center;
}

.about-team .team-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem;
    margin-top: 1.2rem;
}

.team-member {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    text-align: center;
    flex: 1 1 120px;
    max-width: 150px;
}

.team-member img {
    width: 72px;
    height: 72px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid #0d1f3c;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.team-member span {
    font-size: 1rem;
    color: #1a1a1a;
}

.team-member small {
    color: #5b5b5b;
    font-size: 0.85em;
}

.about-testimonials blockquote {
    font-style: italic;
    color: #1f2937;
    background: #ffffff;
    border-left: 4px solid #0d1f3c;
    margin: 1rem 0;
    padding: 1rem 1.2rem;
    border-radius: 0.5rem;
    position: relative;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.04);
}

.about-testimonials footer {
    display: block;
    margin-top: 0.5rem;
    color: #555555;
    font-size: 0.95em;
    text-align: right;
}

/* Responsive Adjustments */
@media (max-width: 768px) {
    .container-desc {
        padding: 2rem 1rem;
    }

    .about-title {
        font-size: 2rem;
    }

    .about-text {
        font-size: 1rem;
    }

    .about-features li {
        font-size: 0.95rem;
        flex-direction: row;
        justify-content: flex-start;
        padding-left: 1rem;
    }

    .team-member {
        max-width: 100%;
        flex: 1 1 100%;
    }

    .about-mission h3,
    .about-team h3,
    .about-testimonials h3 {
        font-size: 1.25rem;
    }

    .about-mission,
    .about-team,
    .about-testimonials {
        padding: 1.2rem 1rem;
    }

    .about-team .team-list {
        flex-direction: column;
        align-items: center;
    }
}

@media (max-width: 480px) {
    .about-title {
        font-size: 1.8rem;
    }

    .about-text {
        font-size: 0.95rem;
    }

    .about-testimonials blockquote {
        font-size: 0.95rem;
        padding: 0.8rem 1rem;
    }

    .team-member img {
        width: 64px;
        height: 64px;
    }

    .team-member span {
        font-size: 0.95rem;
    }
}

</style>