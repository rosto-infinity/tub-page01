<script setup>
  import JobData from './jobs.json'; 
  import { ref } from 'vue';

  const jobs =ref(JobData);
  // console.log(jobs.value[0].company.description);
  
</script>


<template>
  Job listings
</template>


