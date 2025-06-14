<template>
    <Head title="About" />
    <NavBar />

    <MainNav />
    
    <HeroSection />

    <Descript />
        
    <Footer />
</template>
<script>
import { Head } from '@inertiajs/vue3'
import NavBar from '@/Layouts/NavBar.vue';
import MainNav from '@/Layouts/MainNav.vue';
import Footer from '@/Layouts/Footer.vue';  
import HeroSection from './partials/HeroSection.vue';
import Descript from './partials/Descript.vue';

export default {
    name: 'About',
    components: {
        NavBar,
        MainNav,
        HeroSection,
        Descript,
        Footer,
    },
}; 

</script>

<style scoped>

</style>