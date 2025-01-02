<script setup>
import {RouterLink} from 'vue-router';
import JobListing from './JobListing.vue';
import { reactive, onMounted } from 'vue';


import PulseLoader from 'vue-spinner/src/PulseLoader.vue';
import axios from 'axios';

defineProps({
  limit: Number,
  showButton:{ Boolean, default: true}
})
const state = reactive({
  jobs: [],
  isLoading:true
});
// console.log(jobs.value[0].company.description);

onMounted(async () => {
  try{
    const response = await axios.get('/api/jobs');
    state.jobs= response.data;
  } catch (error){
    console.error('Error fetching jobs', error);

  //   try {
  //   const response = await axios.get('http://localhost:5000/jobs');
  //   // Simulate a 2-second delay
  //   await new Promise((resolve) => setTimeout(resolve, 3000));
  //   state.jobs = response.data;
  // } catch (error) {
  //   console.error('Error fetching jobs:', error);

  }finally{
    state.isLoading = false;
  }
});
</script>


<template>
  <section class="bg-blue-50 px-4 py-10">
    <div class="container-xl mx-auto lg:container">
      <h2 class="mb-6 text-center text-3xl font-bold text-green-500 underline" >Parcourir les offres d'emploi</h2>
      <!-- Show loader when loading -->
      <div v-if="state.isLoading" class="flex justify-center">
        <PulseLoader color="#07e283" />
      </div>
      
      <div v-else class="grid grid-cols-1 gap-6 md:grid-cols-3">
        <JobListing v-for="job in state.jobs.slice(0, limit || state.jobs.length)"
         :key="job.id"
         :job="job" />
      </div>
    </div>
  </section>
  
  <section v-if="showButton"
  class="m-auto my-10 max-w-lg px-6">
      <RouterLink
        to="/jobs"
        class="block rounded-xl bg-black px-6 py-4 text-center text-white hover:bg-gray-700"
        >Voir tous les emplois</RouterLink
      >
    </section>
</template>
