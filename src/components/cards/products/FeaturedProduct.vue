<!-- src/components/FeaturedProduct.vue -->
<template>
    <div class="featured-product">
        <div class="featured-box">
            <div class="featured-new">NEW</div>
            <img :src="product.image" alt="featured image" class="featured-img" />
        </div>

        <div class="featured-data">
            <h3 class="featured-name">{{ product.name }}</h3>
            <span class="featured-price">{{ product.price }}</span>
        </div>
    </div>
</template>

<script setup>
defineProps({
    product: {
        type: Object,
        required: true
    }
});
</script>

<style scoped>
</style>
