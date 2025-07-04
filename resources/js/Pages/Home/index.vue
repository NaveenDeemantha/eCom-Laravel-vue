<template>
    <Head title="Home" />
    <NavBar />

    <MainNav />

    <div class="page-content">
        <HeroSection />

        <StylesGrid />

        <ProductList />
    </div>

    <Footer />


</template>

<script>

import { Head } from '@inertiajs/vue3'
import NavBar from '@/Layouts/NavBar.vue';
import MainNav from '@/Layouts/MainNav.vue';
import HeroSection from './partials/HeroSection.vue';
import { usePage } from '@inertiajs/vue3';  
import StylesGrid from './partials/StylesGrid.vue';
import ProductList from './partials/ProductList.vue';
import Footer from '@/Layouts/Footer.vue';

export default {
    name: 'Home',
    components: {
        NavBar,
        MainNav,
        HeroSection,
        StylesGrid,
        ProductList,
        Footer,
    },
    computed: {
        canRegister() {
            return usePage().props.canRegister;
        },
    },
};

</script>

<style scoped>
.page-content {
    margin-top: 90px; /* Adjust as needed for your nav height */
}
</style>