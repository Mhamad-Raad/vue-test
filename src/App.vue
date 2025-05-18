<script setup>
import Navbar from './components/structure/Navbar.vue';
import Footer from './components/structure/Footer.vue';
</script>

<template>
  <main class="flex flex-col min-h-screen">
    <Navbar />
    <router-view />
    <Footer />
  </main>
</template>

