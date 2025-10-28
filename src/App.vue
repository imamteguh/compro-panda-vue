<template>
  <div>
    <Navbar />
    <Hero />
    <About />
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';

import Hero from './components/Hero.vue';
import Navbar from './components/Navbar.vue';
import About from './components/About.vue';

onMounted(() => {
  AOS.init({
    duration: 800,
    easing: 'ease-in-out',
    once: true,
    offset: 100,
  });
})
</script>