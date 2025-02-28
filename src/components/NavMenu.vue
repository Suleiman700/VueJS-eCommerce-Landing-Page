<script setup>
// Mobile Menu
import {onMounted} from "vue";

onMounted(() => {
    const showMenu = (toggleId, navId) => {
        const toggle = document.getElementById(toggleId);
        const nav = document.getElementById(navId);

        if (toggle && nav) {
            toggle.addEventListener('click', () => {
                nav.classList.toggle('show');
            });
        }
    }

    showMenu('nav-toggle', 'nav-menu');

    // Toggling Mobile Menu when a navlink is clicked
    const navLinks = document.querySelectorAll('.nav-link');

    function linkAction(event) {
        navLinks.forEach(n => n.classList.remove('active'))
        event.target.classList.add('active');

        const navMenu = document.getElementById('nav-menu');
        navMenu.classList.remove('show');
    }

    navLinks.forEach(n => n.addEventListener('click', linkAction));
});
</script>

<template>
    <div class="nav-menu" id="nav-menu">
        <ul class="nav-list">
            <li class="nav-item"><a href="#home" class="nav-link active">Home</a></li>
            <li class="nav-item"><a href="#featured" class="nav-link">Featured</a></li>
            <li class="nav-item"><a href="#new" class="nav-link">New</a></li>
            <li class="nav-item"><a href="#subscribed" class="nav-link">Subscribed</a></li>
        </ul>
    </div>
</template>

<style scoped>

</style>