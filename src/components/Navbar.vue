<script setup>
import { RouterLink } from 'vue-router';
import logo from '../assets/img/logo.png'

</script>

<template>
  <nav class="sticky top-0 z-10 border-b border-green-500 bg-green-700 shadow-lg">
      <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
        <div class="flex h-20 items-center justify-between">
          <div
            class="flex flex-1 items-center justify-center md:items-stretch md:justify-start"
          >
            <!-- Logo -->
            <RouterLink class="mr-4 flex flex-shrink-0 items-center" to="/">
            <div class="flex h-12 w-12 items-center justify-center rounded-full bg-white">
              <img class="h-8 w-auto" :src="logo" alt="Vue Jobs" />
            </div>
              <span class="ml-2 hidden text-2xl font-bold text-white md:block"
                >Devinsto</span
              >
            </RouterLink>
            <div class="md:ml-auto">
              <div class="flex space-x-2">
                <RouterLink
                  to="/"
                  class="rounded-md bg-green-900 px-3 py-2 text-white hover:bg-gray-900 hover:text-white"
                  >Home</RouterLink
                >
                <RouterLink
                  to="/jobs"
                  class="rounded-md px-3 py-2 text-white hover:bg-green-900 hover:text-white"
                  >Jobs</RouterLink
                >
                <RouterLink
                  to="jobs/add"
                  class="rounded-md px-3 py-2 text-white hover:bg-green-900 hover:text-white"
                  >Add Job</RouterLink
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
</template>



