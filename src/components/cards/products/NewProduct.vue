<!-- src/components/NewProduct.vue -->
<template>
    <div class="new-box">
        <img :src="product.image" alt="new image" class="new-img" />
        <div class="new-link">
            <a :href="product.link" class="button" style="cursor: pointer;">VIEW PRODUCT</a>
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
