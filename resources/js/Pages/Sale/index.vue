<template>
    <Head title="Sale" />
    <NavBar />
    <MainNav />
    <div class="page-content">
        <HeroSection />
        <SaleProducts />
    </div>
    <Footer />
</template>

<script>
import { Head } from '@inertiajs/vue3'
import NavBar from '@/Layouts/NavBar.vue';
import MainNav from '@/Layouts/MainNav.vue';
import HeroSection from './partials/HeroSection.vue';
import SaleProducts from './partials/SaleProducts.vue';
import Footer from '@/Layouts/Footer.vue';

export default {
    name: 'Sale',
    components: {
        NavBar,
        MainNav,
        HeroSection,
        SaleProducts,
        Footer,
    },
};
</script>

<style scoped>
.page-content {
    margin-top: 120px; /* Consistent with other pages */
}
</style>
