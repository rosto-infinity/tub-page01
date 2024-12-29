<script setup>

import logo from '../assets/img/logo.png'

</script>

<template>
  <nav class="bg-green-700 border-b border-green-500">
      <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
        <div class="flex h-20 items-center justify-between">
          <div
            class="flex flex-1 items-center justify-center md:items-stretch md:justify-start"
          >
            <!-- Logo -->
            <a class="flex flex-shrink-0 items-center mr-4" href="index.html">
            <div class="w-12 h-12 bg-white rounded-full flex items-center justify-center">
              <img class="h-8 w-auto" :src="logo" alt="Vue Jobs" />
            </div>
              <span class="hidden md:block text-white text-2xl font-bold ml-2"
                >Devinsto</span
              >
            </a>
            <div class="md:ml-auto">
              <div class="flex space-x-2">
                <a
                  href="index.html"
                  class="text-white bg-green-900 hover:bg-gray-900 hover:text-white rounded-md px-3 py-2"
                  >Home</a
                >
                <a
                  href="jobs.html"
                  class="text-white hover:bg-green-900 hover:text-white rounded-md px-3 py-2"
                  >Jobs</a
                >
                <a
                  href="add-job.html"
                  class="text-white hover:bg-green-900 hover:text-white rounded-md px-3 py-2"
                  >Add Job</a
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
</template>



