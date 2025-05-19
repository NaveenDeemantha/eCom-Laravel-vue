<template>
    <NavBar />

    <HeroSection />

    <StylesGrid />


</template>

<script>
import NavBar from '@/Layouts/NavBar.vue';
import HeroSection from './partials/HeroSection.vue';
import { usePage } from '@inertiajs/vue3';  
import StylesGrid from './partials/StylesGrid.vue';

export default {
    name: 'Home',
    components: {
        NavBar,
        HeroSection,
        StylesGrid,
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