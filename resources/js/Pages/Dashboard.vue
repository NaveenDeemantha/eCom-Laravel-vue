<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <div class="dashboard-hero">
                <h1 class="dashboard-hero-title">👋 Welcome Back, Admin!</h1>
                <p class="dashboard-hero-subtitle">Your Admin dashboard is ready ✨</p>
            </div>
        </template>

        <div class="dashboard-wrapper">
            <div class="dashboard-card">
                <div class="dashboard-card-glass">
                    <div class="dashboard-icon">
                        <svg
                            class="icon"
                            fill="none"
                            stroke="currentColor"
                            stroke-width="1.5"
                            viewBox="0 0 24 24"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                d="M9.75 17.25L6 21m0 0l-3.75-3.75M6 21V3m12 0l3.75 3.75M18 3l-3.75 3.75M18 3v18"
                            />
                        </svg>
                    </div>
                    <div class="dashboard-text">
                        <h2 class="card-title">You're logged in!</h2>
                        <p class="card-message">
                            Dive into your tools, stats, and settings using the sidebar.
                            Let’s make something awesome today 🚀
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<style scoped>
/* Background */
.dashboard-wrapper {
    background: linear-gradient(135deg, #667eea, #764ba2);
    min-height: calc(100vh - 64px);
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2rem;
}

/* Hero Section */
.dashboard-hero {
    text-align: center;
    margin-top: 2rem;
}

.dashboard-hero-title {
    font-size: 2.25rem;
    font-weight: 800;
    color: #1f2937;
    animation: fadeInDown 0.6s ease-out;
}

.dashboard-hero-subtitle {
    color: #6b7280;
    font-size: 1rem;
    margin-top: 0.5rem;
    animation: fadeIn 1.2s ease-in;
}

/* Glassmorphism Card */
.dashboard-card {
    width: 100%;
    max-width: 720px;
}

.dashboard-card-glass {
    background: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(15px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 20px;
    padding: 2rem;
    box-shadow: 0 20px 50px rgba(0, 0, 0, 0.2);
    display: flex;
    align-items: center;
    gap: 1.5rem;
    animation: floatUp 1s ease-out;
    color: white;
}

.dashboard-icon .icon {
    width: 4rem;
    height: 4rem;
    color: #ffffff;
    opacity: 0.85;
}

.card-title {
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 0.25rem;
}

.card-message {
    font-size: 0.95rem;
    opacity: 0.9;
}

/* Animations */
@keyframes fadeInDown {
    from {
        opacity: 0;
        transform: translateY(-20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes floatUp {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}
</style>
