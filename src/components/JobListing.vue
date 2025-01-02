<script setup>

// Ce code Vue.js définit un composant JobListing qui affiche une description de poste avec la possibilité de basculer entre une description tronquée et une description complète. Voici une explication détaillée :
import{RouterLink} from 'vue-router';
import { ref, computed } from 'vue'
const props = defineProps({
  job: Object
});
const showFullDescription = ref(false);

const toggleFullDescription = () => {
  showFullDescription.value = !showFullDescription.value;
};

const truncatedDescription = computed(() => {
 let description = props.job.description;
  if (!showFullDescription.value) {
    description = description.substring(0, 90) + '...';
  }
  return description;
});
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
              <div>
                {{ truncatedDescription}}
              </div><button class="mb-5 text-green-500 hover:text-green-600" @click="toggleFullDescription">
                <!-- <span v-if="!showFullDescription">Lire plus</span>
                <span v-else>Cacher</span> -->
                {{ showFullDescription ? 'Cacher' : 'Lire plus'}}
              </button>
              </div>

              <h3 class="mb-2 text-green-500">{{ job.salary}}  / An</h3>

              <div class="mb-5 border border-gray-100"></div>

              <div class="mb-4 flex flex-col justify-between lg:flex-row">
                <div class="mb-3 text-orange-700">
                  <i class="pi pi-map-marker text-orange-700"></i>
                  {{ job.location}}
                </div>
                <RouterLink
                  :to="'/jobs/' + job.id"
                  class="h-[36px] rounded-lg bg-green-500 px-4 py-2 text-center text-sm text-white hover:bg-green-600"
                >
                  En savoir plus
                </RouterLink>
              </div>
            </div>
          </div>
</template>