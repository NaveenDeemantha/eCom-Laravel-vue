<template>
  <header :class="['navbar', { scrolled: isScrolled }]">
    <div class="navbar-container">
      <!-- Logo and Brand -->
      <div class="logo" :class="{ 'black-logo': isScrolled }">
        <img src="/images/logo1.png" alt="Logo" />
        <span class="brand-name">HOOMANS</span>
      </div>

      <!-- Desktop Navigation -->
      <nav class="nav-links desktop-only">
        <Link href="/" :class="isScrolled ? 'black' : 'white'">Home</Link>
        <a href="#categories" :class="isScrolled ? 'black' : 'white'">Categories</a>
        <a href="#sale" :class="isScrolled ? 'black' : 'white'">Sale</a>
        <Link href="/about" :class="isScrolled ? 'black' : 'white'">About Us</Link>
        <Link href="/contact" :class="isScrolled ? 'black' : 'white'">Contact Us</Link>
      </nav>

      <!-- Hamburger Icon -->
      <div class="hamburger-button mobile-only" :class="{ 'active': showMobileMenu }" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </div>

    </div>

    <!-- Mobile Nav Menu -->
    <div v-if="showMobileMenu" class="mobile-nav">
      <Link href="/" @click="closeMenu">Home</Link>
      <a href="#categories" @click="closeMenu">Categories</a>
      <a href="#sale" @click="closeMenu">Sale</a>
      <Link href="/about" @click="closeMenu">About Us</Link>
      <Link href="/contact" @click="closeMenu">Contact Us</Link>
    </div>
  </header>
</template>



<script setup>
/*
import { ref, onMounted, onUnmounted } from 'vue'
import { Link } from '@inertiajs/vue3'

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
*/
import { ref, onMounted, onUnmounted } from 'vue'
import { Link } from '@inertiajs/vue3'

const isScrolled = ref(false)
const showMobileMenu = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 10
}

const toggleMenu = () => {
  showMobileMenu.value = !showMobileMenu.value
}

const closeMenu = () => {
  showMobileMenu.value = false
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
  background: rgba(20, 20, 30, 0.55); /* blackish transparent */
  box-shadow: 0 2px 16px rgba(0,0,0,0.13);
  backdrop-filter: blur(14px); /* blur effect */
  -webkit-backdrop-filter: blur(14px);
  z-index: 999;
}

.navbar.scrolled {
  background-color: rgba(255, 255, 255, 0.7); /* semi-transparent white */
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(12px); /* blur effect */
  -webkit-backdrop-filter: blur(12px); /* Safari support */
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.brand-name {
  font-family: 'Nura', sans-serif;
  font-size: 2rem;
  font-weight: bold;
  letter-spacing: 2px;
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
  font-size: 1.3rem;
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

/* Responsive Visibility */
.desktop-only {
  display: flex;
}

.mobile-only {
  display: none;
}

@media (max-width: 768px) {
  .desktop-only {
    display: none;
  }

  .mobile-only {
    display: block;
  }
}

/* Hamburger Icon */
.hamburger {
  cursor: pointer;
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.bar {
  width: 25px;
  height: 3px;
  background-color: white;
  transition: background-color 0.3s ease;
}

.scrolled-bar {
  background-color: black;
}

/* Mobile Nav Panel */
.mobile-nav {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
  background-color: white;
  position: absolute;
  top: 100%;
  left: 0;
  width: 100%;
  padding: 1.5rem 2rem;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
  z-index: 998;
}

.mobile-nav a {
  text-decoration: none;
  font-size: 1.1rem;
  color: #0a0a0a;
  font-weight: 600;
}

.mobile-nav a:hover {
  color: #0d1f3c;
}

.hamburger-button {
  width: 30px;
  height: 20px;
  position: relative;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
  display: none; /* Hide by default, only show in mobile */
  flex-direction: column;
  justify-content: space-between;
}

.hamburger-button span {
  display: block;
  height: 3px;
  width: 100%;
  background-color: black; /* or white; dynamic color can be added */
  border-radius: 3px;
  transition: all 0.3s ease-in-out;
  transform-origin: center;
}

.hamburger-button.active span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger-button.active span:nth-child(2) {
  opacity: 0;
}

.hamburger-button.active span:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

@media (max-width: 768px) {
  .hamburger-button {
    display: flex;
  }
}

/* Mobile nav transitions */
.mobile-nav {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
  background-color: white;
  position: absolute;
  top: 100%;
  left: 0;
  width: 100%;
  padding: 1.5rem 2rem;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
  z-index: 998;
  animation: fadeSlideDown 0.3s ease forwards;
}

@keyframes fadeSlideDown {
  0% {
    opacity: 0;
    transform: translateY(-10%);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Hover animation for links */
.nav-links a,
.mobile-nav a {
  text-decoration: none;
  font-size: 1.1rem;
  color: #0a0a0a;
  font-weight: 600;
  position: relative;
  transition: color 0.3s ease;
}

.nav-links a::after,
.mobile-nav a::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -4px;
  width: 0%;
  height: 2px;
  background-color: #2563eb;
  transition: width 0.3s ease;
}

.nav-links a:hover::after,
.mobile-nav a:hover::after {
  width: 100%;
}


</style>
