<script setup>
import { defineProps } from 'vue';
 defineProps({
  title: {
     type: String,
     default: 'Devenez un développeur Vue',
 },
  subtitle: {
     type: String,
     default: 'Trouvez l\'emploi Vue qui correspond à vos compétences et à vos besoins',
 },
 });
</script>



<template>
  <!-- Hero -->
  <section class="mb-4 bg-[#0a1a0a] py-20">
      <div
        class="mx-auto flex max-w-7xl flex-col items-center px-4 sm:px-6 lg:px-8"
      >
        <div class="text-center">
          <h1
            class="text-4xl font-extrabold text-[#07e283] sm:text-6xl md:text-7xl"
          >
          {{ title }}
          </h1>
          <p class="my-4 text-xl text-white">
            {{ subtitle }}
          </p>
        </div>
      </div>
    </section>
    
</template>



