<template>
    <Head title="About" />
    <NavBar />

    <MainNav />
    
    <div class="page-content">
        <HeroSection />

        <Descript />
        
        <StatsSection />
        
        <ValuesSection />
        
        <TimelineSection />
        
        <PartnersSection />
    </div>
        
    <Footer />
</template>
<script>
import { Head } from '@inertiajs/vue3'
import NavBar from '@/Layouts/NavBar.vue';
import MainNav from '@/Layouts/MainNav.vue';
import Footer from '@/Layouts/Footer.vue';  
import HeroSection from './partials/HeroSection.vue';
import Descript from './partials/Descript.vue';
import StatsSection from './partials/StatsSection.vue';
import ValuesSection from './partials/ValuesSection.vue';
import TimelineSection from './partials/TimelineSection.vue';
import PartnersSection from './partials/PartnersSection.vue';

export default {
    name: 'About',
    components: {
        NavBar,
        MainNav,
        HeroSection,
        Descript,
        StatsSection,
        ValuesSection,
        TimelineSection,
        PartnersSection,
        Footer,
    },
}; 

</script>

<style scoped>
.page-content {
    margin-top: 90px; /* Consistent with other pages */
}
</style>