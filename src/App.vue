<script setup>
import {onMounted, ref} from 'vue'
import FeaturedProduct from './components/cards/products/FeaturedProduct.vue'
import NewProduct from './components/cards/products/NewProduct.vue'
import 'boxicons'
import NavMenu from "@/components/NavMenu.vue";


// Sample product data
const featuredProducts = ref([
    {
        name: 'Product 1',
        image: 'https://i.postimg.cc/ydMgrWqS/feature1.png',
        price: '$20'
    },
    {
        name: 'Product 2',
        image: 'https://i.postimg.cc/PJbx34zB/feature2.png',
        price: '$30'
    },
    {
        name: 'Product 3',
        image: 'https://i.postimg.cc/KvF4K6mF/feature3.png',
        price: '$40'
    },
    {
        name: 'Product 3',
        image: 'https://i.postimg.cc/RZp0DqKV/feature4.png',
        price: '$40'
    },
]);

const newProducts = ref([
    {
        image: 'https://i.postimg.cc/Hs5KNNMJ/new1.png'
    },
    {
        image: 'https://i.postimg.cc/sXq66PD9/new2.png'
    },
    {
        image: 'https://i.postimg.cc/rs4hvdD6/new3.png'
    },
    {
        image: 'https://i.postimg.cc/sDFH5JL3/new4.png'
    },
    {
        image: 'https://i.postimg.cc/Bnph9fnv/new5.png'
    },
    {
        image: 'https://i.postimg.cc/SKtDRL8F/new6.png'
    },
]);

const sponsorLogos = ref([
    'https://i.postimg.cc/3Jv5TRsx/logo1.png',
    'https://i.postimg.cc/bJBWXcLn/logo2.png',
    'https://i.postimg.cc/J0HgM6d2/logo3.png',
    'https://i.postimg.cc/xjkTX9wW/logo4.png',
]);

const productData = {
    name: 'test'
};
</script>

<template>
    <header class="l-header">
        <nav class="nav bd-grid">
            <div>
                <a href="#" class="nav-logo">SARA</a>
            </div>

            <NavMenu />

            <div class="nav-icons">
                <box-icon class='bx bxs-cart nav-cart' name="cart"></box-icon>
                <box-icon class="bx bx-menu nav-toggle" name="menu" id="nav-toggle"></box-icon>
            </div>
        </nav>
    </header>

    <main class="l-main">
        <section class="home" id="home">
            <div class="home-container bd-grid">
                <div class="home-data">
                    <h1 class="home-title">NEW <br><span>ARRIVALS</span></h1>
                    <a href="#featured" class="button">GO SHOPPING</a>
                </div>
                <img src="https://cdn3d.iconscout.com/3d/premium/thumb/man-using-e-commerce-app-3d-illustration-download-in-png-blend-fbx-gltf-file-formats--online-shopping-application-pack-illustrations-6241788.png" alt="image" class="home-img" style="width: 30%;">
            </div>
        </section>

        <section class="collection section">
            <div class="collection-container bd-grid">
                <div class="collection-box">
                    <img src="https://i.postimg.cc/Df1KXmz4/backpack-Man.png" alt="image" class="collection-img">
                    <div class="collection-data">
                        <h2 class="collection-title"><span class="collection-subtitle">Men</span><br>Backpack</h2>
                        <a href="#" class="collection-view">View Collection</a>
                    </div>
                </div>

                <div class="collection-box">
                    <div class="collection-data">
                        <h2 class="collection-title"><span class="collection-subtitle">Women</span><br>Backpack</h2>
                        <a href="#" class="collection-view">View Collection</a>
                    </div>
                    <img src="https://i.postimg.cc/tT0MqtWS/backpack-Woman.png" alt="image" class="collection-img">
                </div>
            </div>
        </section>

        <section class="featured section" id="featured">
            <h2 class="section-title">FEATURED PRODUCT</h2>
            <a href="#" class="section-all">View All</a>

            <div class="featured-container bd-grid">
                <!-- Loop through featured products -->
                <div v-for="(product, index) in featuredProducts" :key="index">
                    <FeaturedProduct
                        :key="index"
                        :product="product"
                    />
                </div>
            </div>
        </section>

        <section class="offer section">
            <div class="offer-bg">
                <div class="offer-data">
                    <h2 class="offer-title">Special Offer</h2>
                    <p class="offer-description">Special offerts discounts for women this week only</p>
                    <a href="#" class="button">SHOP NOW</a>
                </div>
            </div>
        </section>

        <section class="new section" id="new">
            <h2 class="section-title">NEW ARRIVALS</h2>
            <a href="#" class="section-all">View All</a>

            <div class="new-container bd-grid">
                <!-- Loop through new products -->
                <div v-for="(newProduct, index) in newProducts" :key="index" class="new-box">
                    <NewProduct
                        :key="index"
                        :product="newProduct"
                    />
                </div>
            </div>
        </section>

        <section class="newsletter section" id="subscribed">
            <div class="newsletter-container bd-grid">
                <div class="newsletter-subscribe">
                    <h2 class="section-title">OUR NEWSLETTER</h2>
                    <p class="newsletter-description">Promotion news products and sales. Directly to you</p>

                    <form action="" class="newsletter-form">
                        <input type="text" class="newsletter-input" placeholder="Enter your email">
                        <a href="#" class="button">SUBSCRIBE</a>
                    </form>
                </div>
            </div>
        </section>

        <section class="sponsors section">
            <div class="sponsors-container bd-grid">
                <!-- Loop through sponsor logos -->
                <div v-for="(logo, index) in sponsorLogos" :key="index" class="sponsors-logo">
                    <img :src="logo" alt="image logo">
                </div>
            </div>
        </section>
    </main>

    <footer class="footer section">
        <div class="footer-container bd-grid">
            <div class="footer-box">
                <h3 class="footer-title">SARA</h3>
                <p class="footer-deal">Products Store</p>
                <a href="#"><img src="https://i.postimg.cc/sgtFn03x/footerstore1.png" alt="image" class="footer-store"></a>
                <a href="#"><img src="https://i.postimg.cc/pd8w3YdZ/footerstore2.png" alt="image" class="footer-store"></a>
            </div>

            <div class="footer-box">
                <h3 class="footer-title">EXPLORE</h3>
                <ul>
                    <li><a href="#" class="footer-link">Home</a></li>
                    <li><a href="#" class="footer-link">Featured</a></li>
                    <li><a href="#" class="footer-link">New</a></li>
                    <li><a href="#" class="footer-link">Subscribe</a></li>
                </ul>
            </div>

            <div class="footer-box">
                <h3 class="footer-title">OUR SERVICES</h3>
                <ul>
                    <li><a href="#" class="footer-link">Pricing</a></li>
                    <li><a href="#" class="footer-link">Free Shipping</a></li>
                    <li><a href="#" class="footer-link">Gift Cards</a></li>
                </ul>
            </div>

            <div class="footer-box">
                <h3 class="footer-title">FOLLOW US</h3>
                <a href="#" class="footer-social"><i class='bx bxl-facebook'></i></a>
                <a href="#" class="footer-social"><i class='bx bxl-instagram'></i></a>
                <a href="#" class="footer-social"><i class='bx bxl-youtube'></i></a>
            </div>
        </div>

        <p class="footer-copy">&#169; 2024 Copyright All rights reserved</p>
    </footer>
</template>

<style scoped>
/* Your styles here */
</style>
