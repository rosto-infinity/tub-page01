<script setup>

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
            <a class="mr-4 flex flex-shrink-0 items-center" href="index.html">
            <div class="flex h-12 w-12 items-center justify-center rounded-full bg-white">
              <img class="h-8 w-auto" :src="logo" alt="Vue Jobs" />
            </div>
              <span class="ml-2 hidden text-2xl font-bold text-white md:block"
                >Devinsto</span
              >
            </a>
            <div class="md:ml-auto">
              <div class="flex space-x-2">
                <a
                  href="/"
                  class="rounded-md bg-green-900 px-3 py-2 text-white hover:bg-gray-900 hover:text-white"
                  >Home</a
                >
                <a
                  href="/jobs"
                  class="rounded-md px-3 py-2 text-white hover:bg-green-900 hover:text-white"
                  >Jobs</a
                >
                <a
                  href="jobs/add"
                  class="rounded-md px-3 py-2 text-white hover:bg-green-900 hover:text-white"
                  >Add Job</a
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
</template>



