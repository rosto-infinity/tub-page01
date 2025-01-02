<script setup>
  import PulseLoader from 'vue-spinner/src/PulseLoader.vue';
  import {reactive, onMounted} from 'vue';
  import { useRoute, RouterLink} from 'vue-router';
  import axios from 'axios';
  
  const route = useRoute();

  const jobId = route.params.id;
  
  const state = reactive({
    job: {},
    isLoading: true,
  });

  onMounted(async () => {
  try{
    const response = await axios.get(`http://localhost:5000/jobs/${jobId}`);
    // await new Promise((resolve) => setTimeout(resolve, 3000));
    state.job= response.data;

  } catch (error){
    console.error('Error fetching job', error);
  }finally{
    state.isLoading = false;
  }
});
</script>
<template>

  <section class="bg-green-50">
    <div class="container m-auto px-6 py-10">
      <div class="gridcols grid w-full grid-cols-1 gap-6 md:grid-cols-2">
        
         <!-- Show loader when loading -->
      <div v-if="state.isLoading" class="flex justify-center">
        <PulseLoader color="#07e283" />
      </div>
        <!-- Main Content -->
        <main v-else class="">
          <div class="rounded-lg bg-white p-6 text-center shadow-md md:text-left">
            <div class="mb-4 text-gray-500">{{ state.job.type}} </div>
            <h1 class="mb-4 text-3xl font-bold">{{ state.job.title }}</h1>
            <div class="mb-4 flex justify-center align-middle text-gray-500 md:justify-start">
              <i class="fa-solid fa-location-dot mr-2 text-lg text-orange-700"></i>
              <p class="text-orange-700">{{ state.job.location}}</p>
            </div>
          </div>

          <div class="mt-6 rounded-lg bg-white p-6 shadow-md">
            <h3 class="mb-6 text-lg font-bold text-green-800">
              {{ state.job.description}}
            </h3>

            <p class="mb-4">
              We are seeking a talented Front-End Developer to join our team
              in Boston, MA. The ideal candidate will have strong skills in
              HTML, CSS, and JavaScript, with experience working with modern
              JavaScript frameworks such as Vue or Angular.
            </p>

            <h3 class="mb-2 text-lg font-bold text-green-800">Salary</h3>

            <p class="mb-4">{{ state.job.salary}} / Year</p>
          </div>
        </main>

        <!-- Sidebar -->
        <aside class="">
          <!-- Company Info -->
          <div class="rounded-lg bg-white p-6 shadow-md">
            <h3 class="mb-6 text-xl font-bold">Company Info</h3>

            <h2 class="text-2xl">NewTek Solutions</h2>

            <p class="my-2">
              NewTek Solutions is a leading technology company specializing in
              web development and digital solutions. We pride ourselves on
              delivering high-quality products and services to our clients
              while fostering a collaborative and innovative work environment.
            </p>

            <hr class="my-4" />

            <h3 class="text-xl">Contact Email:</h3>

            <p class="my-2 bg-green-100 p-2 font-bold">
              contact@newteksolutions.com
            </p>

            <h3 class="text-xl">Contact Phone:</h3>

            <p class="my-2 bg-green-100 p-2 font-bold">555-555-5555</p>
          </div>

          <!-- Manage -->
          <div class="mt-6 rounded-lg bg-white p-6 shadow-md">
            <h3 class="mb-6 text-xl font-bold">Manage Job</h3>
            <a href="add-job.html"
              class="focus:shadow-outline mt-4 block w-full rounded-full bg-green-500 px-4 py-2 text-center font-bold text-white hover:bg-green-600 focus:outline-none">Edit
              Job</a>
            <button
              class="focus:shadow-outline mt-4 block w-full rounded-full bg-red-500 px-4 py-2 font-bold text-white hover:bg-red-600 focus:outline-none">
              Delete Job
            </button>
          </div>
        </aside>
      </div>
    </div>
  </section>
</template>
<style lang="css" scoped>
  @media (min-width: 768px) {
  .gridcols {
    grid-template-columns: 70% 30%;
  }
}
</style>
