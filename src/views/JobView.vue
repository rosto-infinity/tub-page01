<script setup>
import PulseLoader from 'vue-spinner/src/PulseLoader.vue';
import BackButton from '@/components/BackButton.vue';
import { reactive, onMounted, ref } from 'vue';
import { useRoute, RouterLink, useRouter } from 'vue-router';
import { useToast } from 'vue-toastification';
import axios from 'axios';

const route = useRoute();
const router = useRouter();
const toast = useToast();

const jobId = route.params.id;

const state = reactive({
  job: null,
  isLoading: true,
});

const showDeleteDialog = ref(false);

const deleteJob = async () => {
  try {
    await axios.delete(`/api/jobs/${jobId}`);
    toast.success('Job deleted successfully');
    router.push('/jobs');
  } catch (error) {
    console.error('Erreur lors de la suppression de l\'emploi', error);
    toast.error('An error occurred. Please try again');
  } finally {
    showDeleteDialog.value = false;
  }
};

onMounted(async () => {
  try {
    const response = await axios.get(`/api/jobs/${jobId}`);
    state.job = response.data;
  } catch (error) {
    console.error('Erreur lors de la récupération de l\'emploi', error);
    state.job = null;
  } finally {
    state.isLoading = false;
  }
});
</script>

<template>
  <BackButton />
  <section class="bg-green-50">
    <div class="container m-auto px-6 py-10">
      <div class="gridcols grid w-full grid-cols-1 gap-6 md:grid-cols-2">
        <div v-if="state.isLoading" class="flex justify-center">
          <PulseLoader color="#07e283" />
        </div>
        <main v-else class="">
          <div class="rounded-lg bg-white p-6 text-center shadow-md md:text-left">
            <div class="mb-4 text-gray-500">{{ state.job.type }}</div>
            <h1 class="mb-4 text-3xl font-bold">{{ state.job.title }}</h1>
            <div class="mb-4 flex justify-center align-middle text-gray-500 md:justify-start">
              <i class="pi pi-map-marker location-dot mr-2 text-lg text-orange-700"></i>
              <p class="text-orange-700">{{ state.job.location }}</p>
            </div>
          </div>

          <div class="mt-6 rounded-lg bg-white p-6 shadow-md">
            <h3 class="mb-6 text-lg font-bold text-green-800">Job Description</h3>
            <p class="mb-4">{{ state.job.description }}</p>
            <h3 class="mb-2 text-lg font-bold text-green-800">Salary</h3>
            <p class="mb-4">{{ state.job.salary }} / Year</p>
          </div>
        </main>

        <aside v-if="state.job" class="">
          <div class="rounded-lg bg-white p-6 shadow-md">
            <h3 class="mb-6 text-xl font-bold">Company Info</h3>
            <h2 class="text-2xl">{{ state.job.company.name }}</h2>
            <p class="my-2">{{ state.job.company.description }}</p>
            <hr class="my-4" />
            <h3 class="text-xl">Contact Email:</h3>
            <p class="my-2 bg-green-100 p-2 font-bold">{{ state.job.company.contactEmail }}</p>
            <h3 class="text-xl">Contact Phone:</h3>
            <p class="my-2 bg-green-100 p-2 font-bold">{{ state.job.company.contactPhone }}</p>
          </div>

          <div class="mt-6 rounded-lg bg-white p-6 shadow-md">
            <h3 class="mb-6 text-xl font-bold">Manage Job</h3>
            <RouterLink :to="`/jobs/edit/${jobId}`"
              class="focus:shadow-outline mt-4 block w-full rounded-full bg-green-500 px-4 py-2 text-center font-bold text-white hover:bg-green-600 focus:outline-none">
              Edit Job
            </RouterLink>
            <button @click="showDeleteDialog = true"
              class="focus:shadow-outline mt-4 block w-full rounded-full bg-red-500 px-4 py-2 text-center font-bold text-white hover:bg-red-600 focus:outline-none">
              Delete Job
            </button>
          </div>
        </aside>
      </div>
    </div>
  </section>

  <dialog v-if="showDeleteDialog" class="fixed inset-0 z-50 flex min-h-full min-w-full items-center justify-center bg-[#0a1a0a]/50">
    <div class="mx-4 w-full max-w-md rounded-lg bg-white p-6 shadow-lg sm:p-8">
      <h3 class="mb-4 text-xl font-bold">Confirm Delete</h3>
      <p class="mb-6">Are you sure you want to delete this job?</p>
      <div class="flex justify-end space-x-4">
        <button @click="showDeleteDialog = false"
          class="rounded-full bg-gray-300 px-4 py-2 font-bold text-gray-600 hover:bg-gray-400 focus:outline-none">
          Cancel
        </button>
        <button @click="deleteJob"
          class="rounded-full bg-red-500 px-4 py-2 font-bold text-white hover:bg-red-600 focus:outline-none">
          Supprimer
        </button>
      </div>
    </div>
  </dialog>
</template>

<style lang="css" scoped>
@media (min-width: 768px) {
  .gridcols {
    grid-template-columns: 70% 30%;
  }
}
</style>
