<template>
  <section :class="['section-navbar', { scrolled: isScrolled }]">
    <Head title="Hoomans" />
    <header class="header">
      <nav class="navbar">
        <div class="nav-buttons">
          <Button variant="ghost" asChild>
            <Link :href="route('login')" class="btn-link">Log in</Link>
          </Button>
          <Button asChild>
            <Link v-if="canRegister" :href="route('register')" class="btn-link">Register</Link>
          </Button>
          <Button variant="outline" asChild>
            <Link v-if="$page.props.auth.user" :href="route('dashboard')" class="btn-link">Dashboard</Link>
          </Button>
        </div>
      </nav>
    </header>
  </section>
</template>

<script setup>
import { Head, Link } from '@inertiajs/vue3';
import { usePage } from '@inertiajs/vue3';
import { ref, onMounted, onUnmounted } from 'vue';

const canRegister = usePage().props.canRegister;
const isScrolled = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 10;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
/* Base Section Styling */
.section-navbar {
  position: fixed;
  top: 0;
  width: 100%;
  background-color: rgba(21, 20, 20, 0.95);
  color: #fff;
  padding: 0.5rem 0;
  backdrop-filter: none;
  transition: backdrop-filter 0.3s ease, background-color 0.3s ease;
  z-index: 999;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Blur and transparency when scrolled */
.section-navbar.scrolled {
  background-color: rgba(21, 20, 20, 0.7);
  backdrop-filter: blur(8px);
}

/* Header */
.header {
  font-size: 10px;
  margin: 0 auto;
  padding: 0 2rem;
}

/* Navbar Flex Layout */
.navbar {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  flex-wrap: wrap;
}

/* Navigation Buttons */
.nav-buttons {
  display: flex;
  gap: 0.75rem;
  font-family: 'roboto', sans-serif;
  text-transform: lowercase;
  letter-spacing: 2px;
}

/* Button-like Links */
.btn-link {
  padding: 0.5rem 1rem;
  border-radius: 3px;
  font-weight: 550;
  text-decoration: none;
  color: #fff;
  transition: background 0.8s ease, color 0.3s ease;
}

.btn-link:hover {
  background-color: rgb(255, 255, 255);
  color: #151414;
}
</style>
