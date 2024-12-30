<script setup>
import JobData from './jobs.json';
import { ref } from 'vue';

const jobs = ref(JobData);
// console.log(jobs.value[0].company.description);

</script>


<template>
  <section class="bg-blue-50 px-4 py-10">
    <div class="container-xl lg:container mx-auto">
      <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">Parcourir les offres d'emploi</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div v-for="job in jobs" :key="job.id">
          {{ job.title }}

        </div>

      </div>
    </div>
  </section>

</template>
