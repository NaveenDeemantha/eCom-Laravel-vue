<template>
    <Head title="Contact" />
    <NavBar />
    <MainNav />
    <Footer />
</template>

<script>
import { Head } from '@inertiajs/vue3'
import NavBar from '@/Layouts/NavBar.vue';
import MainNav from '@/Layouts/MainNav.vue';
import Footer from '@/Layouts/Footer.vue';

export default {
    name: 'Contact',
    components: {
        NavBar,
        MainNav,
        Footer,
    },
};
</script>

<style scoped>

</style>
