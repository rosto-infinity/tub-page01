<script setup>
defineProps({
  job: Object
})
</script>
<template>
<!-- Job Listing 1 -->
<div class="relative rounded-xl bg-white shadow-md">
            <div class="p-4">
              <div class="mb-6">
                <div class="my-2 text-gray-600">{{ job.type}}</div>
                <h3 class="text-xl font-bold">{{ job.title}}</h3>
              </div>

              <div class="mb-5">
                {{ job.description}}
              </div>

              <h3 class="mb-2 text-green-500">{{ job.salary}} $ par an</h3>

              <div class="mb-5 border border-gray-100"></div>

              <div class="mb-4 flex flex-col justify-between lg:flex-row">
                <div class="mb-3 text-orange-700">
                  <i class="fa-solid fa-location-dot text-lg"></i>
                  {{ job.location}}
                </div>
                <a
                  href="job.html"
                  class="h-[36px] rounded-lg bg-green-500 px-4 py-2 text-center text-sm text-white hover:bg-green-600"
                >
                  Read More
                </a>
              </div>
            </div>
          </div>
</template>