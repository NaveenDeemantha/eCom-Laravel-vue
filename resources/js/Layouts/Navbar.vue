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
</template>

<script setup>
import { Head, Link } from '@inertiajs/vue3';
import { usePage } from '@inertiajs/vue3';


const canRegister = usePage().props.canRegister;
</script>

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
  max-width: auto;
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
  font-size: 1.5rem;
  font-weight: bold;
  letter-spacing: 5px;
  color: #fff;
}

.brand-name {
  font-family: 'nura', sans-serif;
}

/* Navigation Buttons */
.nav-buttons {
  display: flex;
  gap: 0.75rem;
  font-family: 'nura', sans-serif;
  text-transform: lowercase;
  letter-spacing: 2px;
}

/* Button-like Links */
.btn-link {
  padding: 0.5rem 1rem;
  border-radius: 6px;
  font-weight: 450;
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
</style>