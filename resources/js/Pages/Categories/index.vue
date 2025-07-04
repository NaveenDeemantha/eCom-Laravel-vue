<template>
    <Head title="Categories" />
    <NavBar />
    <MainNav />
    <div class="page-content">
        <Herosection />
        <FeaturedCategories />
        <CategoriesGrid @category-selected="handleCategorySelection" />
        <BrandShowcase />
        <ProductFilter :selected-category="selectedCategory" />
    </div>
    <Footer />
</template>

<script>
import { Head } from '@inertiajs/vue3'
import NavBar from '@/Layouts/NavBar.vue';
import MainNav from '@/Layouts/MainNav.vue';
import Footer from '@/Layouts/Footer.vue';
import Herosection from './partials/herosection.vue';
import FeaturedCategories from './partials/FeaturedCategories.vue';
import CategoriesGrid from './partials/CategoriesGrid.vue';
import BrandShowcase from './partials/BrandShowcase.vue';
import ProductFilter from './partials/ProductFilter.vue';

export default {
    name: 'Categories',
    components: {
        NavBar,
        MainNav,
        Herosection,
        FeaturedCategories,
        CategoriesGrid,
        BrandShowcase,
        ProductFilter,
        Footer,
    },
    data() {
        return {
            selectedCategory: null
        }
    },
    methods: {
        handleCategorySelection(category) {
            this.selectedCategory = category;
        }
    }
};
</script>

<style scoped>
.page-content {
    margin-top: 120px; /* Consistent with other pages */
}
</style>