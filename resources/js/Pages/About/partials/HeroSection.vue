<template>
  <section class="about-hero">
    <div class="image-wrapper">
      <img src="/images/about-hero.jpg" alt="Team working" />
      <div class="overlay-content">
        <h1>About Us</h1>
        <p>We are passionate about creating amazing digital experiences that engage and inspire.</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AboutHero'
}
</script>

<style scoped>
.about-hero {
  width: 100%;
  height: 100vh; /* Full viewport height */
  overflow: hidden;
  position: relative;
}

.image-wrapper {
  width: 100%;
  height: 100%;
  position: relative;
}

.image-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}

.overlay-content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: white;
  text-align: center;
  z-index: 2;
  padding: 1rem;
  text-shadow: 0 2px 8px rgba(0, 0, 0, 0.7);
}

.overlay-content h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.overlay-content p {
  font-size: 1.25rem;
  max-width: 600px;
  margin: auto;
}
</style>
