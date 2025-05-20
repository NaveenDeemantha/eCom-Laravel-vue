<template>
    <NavBar />

    <HeroSection />

    <StylesGrid />

    <ProductList />


</template>

<script>
import NavBar from '@/Layouts/NavBar.vue';
import HeroSection from './partials/HeroSection.vue';
import { usePage } from '@inertiajs/vue3';  
import StylesGrid from './partials/StylesGrid.vue';
import ProductList from './partials/ProductList.vue';

export default {
    name: 'Home',
    components: {
        NavBar,
        HeroSection,
        StylesGrid,
        ProductList
    },
    computed: {
        canRegister() {
            return usePage().props.canRegister;
        },
    },
};

</script>

<style>

</style>