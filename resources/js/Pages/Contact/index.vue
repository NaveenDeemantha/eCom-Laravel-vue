<template>
    <Head title="Contact" />
    <NavBar />
    <MainNav />
    <div class="page-content">
        <HeroSection />
        <ContactForm />
        <FaqSection />
        <NewsletterSection />
    </div>
    <Footer />
</template>

<script>
import { Head } from '@inertiajs/vue3'
import NavBar from '@/Layouts/NavBar.vue';
import MainNav from '@/Layouts/MainNav.vue';
import HeroSection from './partials/HeroSection.vue';
import ContactForm from './partials/ContactForm.vue';
import FaqSection from './partials/FaqSection.vue';
import NewsletterSection from './partials/NewsletterSection.vue';
import Footer from '@/Layouts/Footer.vue';

export default {
    name: 'Contact',
    components: {
        NavBar,
        MainNav,
        HeroSection,
        ContactForm,
        FaqSection,
        NewsletterSection,
        Footer,
    },
};
</script>

<style scoped>
.page-content {
    margin-top: 90px; /* Adjust this value to match the combined height of your NavBar and MainNav */
}
</style>
