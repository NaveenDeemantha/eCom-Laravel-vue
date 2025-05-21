<template>
  <footer class="footer">
    <div class="footer-container">
      
      <!-- Logo & Brand -->
      <div class="footer-logo">
        <img src="/images/logo1.png" alt="Logo" />
        <span class="brand">HOOMANS</span>
      </div>

      
      <div class="footer-links">
        <a href="#home">Home</a>
        <a href="#categories">Categories</a>
        <a href="#sale">Sale</a>
        <a href="#about">About Us</a>
        <a href="#contact">Contact Us</a>
      </div>

      
      <div class="footer-socials">
        <a href="#" title="Instagram">📸</a>
        <a href="#" title="Facebook">📘</a>
        <a href="#" title="Twitter">🐦</a>
      </div>
    </div>

    <div class="footer-bottom">
      <p>© {{ new Date().getFullYear() }} HOOMANS — All rights reserved.</p>
    </div>
  </footer>
</template>

<script setup>
</script>

<style scoped>
.footer {
  background-color: #151414;
  color: #fff;
  padding: 3rem 1rem 1.5rem;
  font-family: 'Roboto', sans-serif;
}

.brand{
    font-family: 'Nura', sans-serif;
}
.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  gap: 2rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  padding-bottom: 1rem;
}

/* Logo */
.footer-logo {
  display: flex;
  align-items: center;
  gap: 0.6rem;
}

.footer-logo img {
  height: 40px;
}

.footer-logo .brand {
  font-size: 1.5rem;
  font-weight: bold;
  letter-spacing: 3px;
}

/* Navigation */
.footer-links {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  font-weight: 500;
}

.footer-links a {
  color: #fff;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: #00bcd4;
}

/* Socials */
.footer-socials {
  display: flex;
  gap: 1rem;
  font-size: 1.3rem;
}

.footer-socials a {
  color: #fff;
  transition: color 0.3s ease;
}

.footer-socials a:hover {
  color: #00bcd4;
}

/* Bottom Text */
.footer-bottom {
  text-align: center;
  margin-top: 1rem;
  font-size: 0.875rem;
  color: #bbb;
}
</style>
