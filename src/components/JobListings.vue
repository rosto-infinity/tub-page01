<script setup>
import JobData from './jobs.json';
import { ref } from 'vue';

const jobs = ref(JobData);
// console.log(jobs.value[0].company.description);

</script>


<template>
  <section class="bg-blue-50 px-4 py-10">
    <div class="container-xl mx-auto lg:container">
      <h2 class="mb-6 text-center text-3xl font-bold text-green-500 underline" >Parcourir les offres d'emploi</h2>
      <div class="grid grid-cols-1 gap-6 md:grid-cols-3">
        <div v-for="job in jobs" :key="job.id">
          {{ job.title }}
        </div>
      </div>
    </div>
  </section>

</template>
