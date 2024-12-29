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
  <section class="bg-green-700 py-20 mb-4">
      <div
        class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col items-center"
      >
        <div class="text-center">
          <h1
            class="text-4xl font-extrabold text-white sm:text-6xl md:text-7xl"
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



