<template>
    <section class="hero-section">
        <video autoplay muted loop playsinline class="bg-video">
            <source src="/videos/hero-video.mp4" type="video/mp4" />
            
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
</template>

<style scoped>
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
</style>