<template>
    <Head title="About" />
    <NavBar />

    <MainNav />
    <br>

    <HeroSection />

    
    <Footer />
</template>
<script>
import { Head } from '@inertiajs/vue3'
import NavBar from '@/Layouts/NavBar.vue';
import MainNav from '@/Layouts/MainNav.vue';
import Footer from '@/Layouts/Footer.vue';  
import HeroSection from './partials/HeroSection.vue';

export default {
    name: 'About',
    components: {
        NavBar,
        MainNav,
        HeroSection,
        Footer,
    },
}; 

</script>

<style scoped>

</style>