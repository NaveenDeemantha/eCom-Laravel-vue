<template>
    <Head title="Home" />
    <NavBar />

    <MainNav />

    <HeroSection />

    <StylesGrid />

    <ProductList />


</template>

<script>

import { Head } from '@inertiajs/vue3'
import NavBar from '@/Layouts/NavBar.vue';
import MainNav from '@/Layouts/MainNav.vue';
import HeroSection from './partials/HeroSection.vue';
import { usePage } from '@inertiajs/vue3';  
import StylesGrid from './partials/StylesGrid.vue';
import ProductList from './partials/ProductList.vue';

export default {
    name: 'Home',
    components: {
        NavBar,
        MainNav,
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