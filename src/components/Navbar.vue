<script setup>
import { RouterLink ,useRoute } from 'vue-router';
import logo from '../assets/img/logo.png'

const isActiveLink = (routePath) => {
  const currentRoute = useRoute();
  return currentRoute.path === routePath;
};
</script>

<template>
  <nav class="sticky top-0 z-10 border-b border-[#07e283] bg-[#0a1a0a] shadow-lg">
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
                  :class="[
                     isActiveLink('/') ?
                     'bg-[#07e283]'
                     :'hover:bg-[#039255] hover:text-white',
                    'rounded-md ','px-3', 'py-2', 'text-white ',
                  ]"
                  
                  >Home</RouterLink
                >
                <RouterLink
                  to="/jobs"
                   :class="[
                     isActiveLink('/jobs') ?
                     'bg-[#07e283]'
                     :'hover:bg-[#039255] hover:text-white',
                    'rounded-md ','px-3', 'py-2', 'text-white ',
                  ]"
                  >Jobs</RouterLink
                >
                <RouterLink
                  to="/jobs/add"
                   :class="[
                     isActiveLink('/jobs/add') ?
                     'bg-[#07e283]'
                     :'hover:bg-[#039255] hover:text-white',
                    'rounded-md ','px-3', 'py-2', 'text-white ',
                  ]"
                  >Add Job</RouterLink
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
</template>



