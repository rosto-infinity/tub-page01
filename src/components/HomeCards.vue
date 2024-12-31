<script setup>
import {RouterLink} from 'vue-router';
import Card from './Card.vue';

</script>


<template>
   <!-- Développeurs and Employeurs -->
   <section class="py-4"> 
      <div class="container-xl m-auto lg:container">
        <div class="grid grid-cols-1 gap-4 rounded-lg p-4 md:grid-cols-2">
          <Card>
            <h2 class="text-2xl font-bold">Pour les développeurs</h2>
            <p class="mb-4 mt-2">
              Parcourez nos offres d'emploi Vue et démarrez votre carrière dès aujourd'hui
            </p>
            <RouterLink
              to="/jobs"
              class="inline-block rounded-lg bg-black px-4 py-2 text-white hover:bg-gray-700"
            >
            Parcourir les emplois
            </RouterLink>
          </Card>
          <Card bg="bg-green-100">
            <h2 class="text-2xl font-bold">Pour les employeurs</h2>
            <p class="mb-4 mt-2">
              Répertoriez votre travail pour trouver le développeur idéal pour le poste
            </p>
            <RouterLink
              to="jobs/add"
              class="inline-block rounded-lg bg-green-500 px-4 py-2 text-white hover:bg-green-600"
            >
              Add Job
            </RouterLink>
          </Card>
        </div>
      </div>
    </section>

</template>


