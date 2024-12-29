 <script setup>
  import Navbar from './components/Navbar.vue';
  import Hero from './components/Hero.vue';
  </script>

<template>
  <Navbar />
  <Hero :title="title" :subtitle="subtitle"/>
</template>