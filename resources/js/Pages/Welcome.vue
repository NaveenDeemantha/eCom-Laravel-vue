<template>
    <section class=section-top>
        <Head title="Hoomans" />
        <header class="header">
            <nav class="navbar">
                <div class="brand-container">
                    <span class="brand-name">Hoomans</span>
                </div>
                <div class="nav-buttons">
                    <Button variant="ghost" asChild>
                        <Link :href="route('login')" class="btn-link ghost">Log in</Link>
                    </Button>
                    <Button asChild>
                        <Link v-if="canRegister" :href="route('register')" class="btn-link ghost">Register</Link>
                    </Button>
                    <Button variant="outline" asChild>
                        <Link v-if="$page.props.auth.user" :href="route('dashboard')" class="btn-link ghost">Dashboard</Link>
                    </Button>
                </div>
            </nav>
        </header>
    </section>

    <section class="hero-section">
        <video autoplay muted loop playsinline class="bg-video">
            <source src="/videos/hero-video.mp4" type="video/mp4" />
            // Your browser does not support the Content Here. //
        </video>

        <div class="overlay"></div>

        <div class="container">
            <div class="row justify-content-center">
            <div class="col-xl-7 col-lg-7 col-md-12">
                <div class="hero-text">
                <h1 class="hero-title">
                    <span class="highlight-dark">Welcome To Hoomans</span>
                    <span class="highlight-primary"></span>
                </h1>
                <p class="hero-subtitle">
                    Born from the concrete jungle, HOOMANS is for the bold, the untamed, the ones who break rules and set trends.
                </p>
                <a href="#" class="btn btn-primary me-2">Explore</a>
                <a href="#" class="btn btn-outline-primary">Shop Now</a>
                </div>
            </div>
            </div>
        </div>
    </section>

    <section class="image-grid">
        <div class="section-wrapper">
            <div class="container">
                <div class="row">
                    <!-- Text Content Container -->
                    <div class="col-xl-6 col-lg-6 col-12">
                        <div class="content-container">
                            <div class="content-box">
                                <h1 class="heading">Shop With Us</h1>
                                <p class="subtitle">
                                    We're looking for incredible people to build on our strong momentum. Help us power the brands you
                                    know and love.
                                </p>
                                <a href="#position" class="btn btn-primary">See All Open Positions</a>
                                <p class="note mt-4 mb-0">
                                    69 open positions across <a href="#">all offices</a> and <a href="#">all teams</a>.
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Image Grid Container -->
                    <div class="col-lg-6 col-12">
                        <div class="images-container">
                            <div class="image-grid-container">
                                <div class="image-grid-item">
                                    <img src="/images/img1.jpg" alt="Grid Image 1" class="grid-image">
                                </div>
                                <div class="image-grid-item">
                                    <img src="/images/img2.jpg" alt="Grid Image 2" class="grid-image">
                                </div>
                                <div class="image-grid-item">
                                    <img src="/images/img3.jpg" alt="Grid Image 3" class="grid-image">
                                </div>
                                <div class="image-grid-item">
                                    <img src="/images/img4.jpg" alt="Grid Image 4" class="grid-image">
                                </div>
                                <div class="image-grid-item">
                                    <img src="/images/img5.jpg" alt="Grid Image 5" class="grid-image">
                                </div>
                                <div class="image-grid-item">
                                    <img src="/images/img6.jpg" alt="Grid Image 6" class="grid-image">
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>



        <!-- <main class="main-content"> -->
        <!-- Add main content here -->
        <!-- </main> -->

        <!--<section class="section-footer">
            <footer class="footer">
                 Hoomans Inc © 2025 . All rights reserved.
            </footer>
        </section> -->
</template>

<style scoped>


/* Base Section Styling */
.section-top {
  background-color: #151414; /* Black background for bold brand feel */
  color: #fff;
  padding: 1rem 0;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

/* Header */
.header {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

/* Navbar Flex Layout */
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
}

/* Brand Styling */
.brand-container {
  font-size: 2rem;
  font-weight: bold;
  letter-spacing: 2.5px;
  color: #fff;
}

.brand-name {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

/* Navigation Buttons */
.nav-buttons {
  display: flex;
  gap: 0.75rem;
}

/* Button-like Links */
.btn-link {
  padding: 0.5rem 1rem;
  border-radius: 6px;
  font-weight: 500;
  text-decoration: none;
  transition: background 0.3s ease, color 0.3s ease;
}

.btn-link:hover {
  background-color: rgba(148, 145, 145, 0.417);
}

/* Specific Button Variants */
.btn-link.ghost {
  color: #fff;
}

.btn-link.solid {
  background-color: #fff;
  color: #000;
}

.btn-link.outline {
  border: 2px solid #fff;
  color: #fff;
}

.btn-link.outline:hover {
  background-color: #fff;
  color: #000;
}


/* Footer 
.footer {
    padding: 4rem 0;
    text-align: center;
    font-size: 0.875rem;
    color: #000000;
}

.dark .footer {
    color: rgba(255, 255, 255, 0.7);
}
*/


/* Stylings for Hero Section */

.hero-section {
  position: relative;
  width: 100%;
  min-height: 90vh;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  text-align: center;
  padding: 4rem 2rem;
}

/* Background Video Styling */
.bg-video {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  object-fit: cover;
  z-index: -2;
}

/* Dark overlay for readability */
.overlay {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.6);
  z-index: -1;
}

/* Hero Text Styling */
.hero-text {
  z-index: 1;
  padding: 2rem;
}

.hero-title {
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.highlight-dark {
  color: #fff;
}

.highlight-primary {
  color: #FF2D20;
}

.hero-subtitle {
  font-size: 1.25rem;
  margin-bottom: 2rem;
  color: #f0f0f0;
}

/* Button Styling (Bootstrap Based) */
.btn-primary {
  background-color: #FF2D20;
  border: none;
  padding: 0.75rem 1.5rem;
  color: #fff;
  font-weight: 600;
  transition: 0.3s ease-in-out;
  border-radius: 8px;
}

.btn-primary:hover {
  background-color: #e5271c;
}

.btn-outline-primary {
  border: 2px solid #FF2D20;
  color: #FF2D20;
  padding: 0.75rem 1.5rem;
  font-weight: 600;
  border-radius: 8px;
  transition: 0.3s ease-in-out;
}

.btn-outline-primary:hover {
  background-color: #FF2D20;
  color: #fff;
}


/* Image Grid Styles*/ 
/* Section Background */
.section-wrapper {
  padding: 4rem 0;
  background-color: #fff;
}

/* Text Styles */
.content-container {
  height: 100%;
  display: flex;
  align-items: center;
  padding: 2rem;
  background-color: #fff;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.content-box {
  width: 100%;
}

.heading {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  color: #333;
}

.subtitle {
  font-size: 1.1rem;
  line-height: 1.6;
  color: #666;
  margin-bottom: 2rem;
}

.note a {
  color: #007bff;
  text-decoration: underline;
}

/* Image Grid Styles */
.images-container {
  height: 100%;
  padding: 2rem;
  background-color: #fff;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.image-grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.image-grid-item {
  aspect-ratio: 1;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.grid-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.grid-image:hover {
  transform: scale(1.05);
}

@media (max-width: 768px) {
  .content-container,
  .images-container {
    margin-bottom: 2rem;
  }
  
  .image-grid-container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 480px) {
  .image-grid-container {
    grid-template-columns: 1fr;
  }
}

</style>


<script setup>
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});

function handleImageError() {
    document.getElementById('screenshot-container')?.classList.add('!hidden');
    document.getElementById('docs-card')?.classList.add('!row-span-1');
    document.getElementById('docs-card-content')?.classList.add('!flex-row');
    document.getElementById('background')?.classList.add('!hidden');
}

</script>

