<script setup>
import { useRoute } from 'vue-router';

const route = useRoute();
</script>

<template>
  <nav class="flex items-center gap-6 bg-gray-800 p-4">
    <router-link
      to="/"
      :class="route.path === '/' ? 'text-yellow-400 font-bold' : 'text-white'"
    >
      Home
    </router-link>
    <router-link
      to="/about"
      :class="
        route.path === '/about' ? 'text-yellow-400 font-bold' : 'text-white'
      "
    >
      About
    </router-link>
  </nav>
</template>
