<template>
  <header :class="['navbar', { scrolled: isScrolled }]">
    <div class="navbar-container">
      <!-- Logo -->
      <div class="logo" :class="{ 'black-logo': isScrolled }">
        <img src="/images/logo1.png" alt="Logo" />
        <span>HOOMANS</span>
      </div>

      <!-- Navigation Links -->
      <nav class="nav-links">
        <a href="#home" :class="isScrolled ? 'black' : 'white'">Home</a>
        <a href="#categories" :class="isScrolled ? 'black' : 'white'">Categories</a>
        <a href="#sale" :class="isScrolled ? 'black' : 'white'">Sale</a>
        <a href="#about" :class="isScrolled ? 'black' : 'white'">About Us</a>
        <a href="#contact" :class="isScrolled ? 'black' : 'white'">Contact Us</a>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 10
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 30px;
  width: 100%;
  padding: 15px 40px;
  transition: background-color 0.3s ease, box-shadow 0.3s ease;
  background-color: transparent;
  z-index: 999;
}

.navbar.scrolled {
  background-color: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  font-size: 20px;
  font-weight: bold;
  color: white;
  transition: color 0.3s ease;
}

.logo.black-logo {
  color: black;
}

.logo img {
  height: 40px;
  margin-right: 10px;
}

.nav-links {
  display: flex;
  gap: 25px;
}

.nav-links a {
  text-decoration: none;
  font-weight: bold;
  transition: color 0.3s ease;
}

.nav-links a.white {
  color: white;
}

.nav-links a.black {
  color: black;
}

.nav-links a:hover {
  color: #007BFF;
}
</style>
