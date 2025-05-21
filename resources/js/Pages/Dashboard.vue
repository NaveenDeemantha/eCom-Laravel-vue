<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <div class="dashboard-header">
                <h1 class="dashboard-title">📊 Admin Dashboard</h1>
                <p class="dashboard-subtitle">Monitor HOOMANS performance at a glance</p>
            </div>
        </template>

        <div class="dashboard-content">
            <!-- Metrics Section -->
            <div class="metrics-grid">
                <div class="card">
                    <h2>Total Sales</h2>
                    <p>$12,540</p>
                    <span class="card-hint">+18% from last month</span>
                </div>
                <div class="card">
                    <h2>New Users</h2>
                    <p>1,203</p>
                    <span class="card-hint">+9.3% increase</span>
                </div>
                <div class="card">
                    <h2>Orders</h2>
                    <p>874</p>
                    <span class="card-hint">+5% from last week</span>
                </div>
                <div class="card">
                    <h2>Traffic</h2>
                    <p>48,590</p>
                    <span class="card-hint">+22% unique visitors</span>
                </div>
            </div>

            <!-- Welcome Box -->
            <div class="welcome-card">
                <h2>Welcome Back, Admin 👋</h2>
                <p>
                    Here's a quick overview of how your HOOMANS brand is performing. Use the sidebar to manage products, orders, and customers.
                </p>
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<style scoped>
/* Overall Background */
.dashboard-content {
    background: #0d0d0d;
    min-height: calc(100vh - 64px);
    padding: 2rem;
    color: #ffffff;
}

/* Header */
.dashboard-header {
    text-align: center;
    padding-top: 1rem;
    padding-bottom: 2rem;
}

.dashboard-header h1 {
    font-family: 'Roboto', sans-serif;
    font-size: 3rem;
    font-weight: 700;
    color: #000000;
}

.dashboard-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: #ffffff;
}

.dashboard-subtitle {
    font-size: 1rem;
    color: #9ca3af;
}

/* Grid for Metrics */
.metrics-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.5rem;
    margin-bottom: 2rem;
}

.card {
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px);
    border-radius: 12px;
    padding: 1.5rem;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-4px);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
}

.card h2 {
    font-size: 1.2rem;
    color: #cccccc;
    margin-bottom: 0.5rem;
}

.card p {
    font-size: 2rem;
    font-weight: bold;
    color: #ffffff;
}

.card-hint {
    font-size: 0.875rem;
    color: #22c55e;
}

/* Welcome Box */
.welcome-card {
    background: linear-gradient(145deg, #1c1c1c, #111);
    border-radius: 12px;
    padding: 2rem;
    text-align: center;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
}

.welcome-card h2 {
    font-size: 1.75rem;
    font-weight: bold;
    margin-bottom: 1rem;
}

.welcome-card p {
    font-size: 1rem;
    color: #cccccc;
    line-height: 1.6;
}

/* Responsive */
@media (max-width: 640px) {
    .dashboard-title {
        font-size: 1.75rem;
    }

    .metrics-grid {
        grid-template-columns: 1fr;
    }

    .card p {
        font-size: 1.5rem;
    }
}
</style>
