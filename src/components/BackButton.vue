<script setup>
import { RouterLink } from 'vue-router';

</script>


<template>
   <!-- Go Back -->
   <section>
      <div class="container m-auto px-6 py-6">
        <RouterLink
          to="/jobs"
          class="flex items-center text-green-500 hover:text-green-600"
        >
          <i class="pi pi-arrow-circle-left mr-2"></i> Back to Job Listings
        </RouterLink>
      </div>
    </section>
</template>


