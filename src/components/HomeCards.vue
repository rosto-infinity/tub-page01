<script setup>
import Card from './Card.vue';

</script>


<template>
   <!-- Developers and Employers -->
   <section class="py-4"> 
      <div class="container-xl lg:container m-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 p-4 rounded-lg">
          <Card>
            <h2 class="text-2xl font-bold">Pour les développeurs</h2>
            <p class="mt-2 mb-4">
              Parcourez nos offres d'emploi Vue et démarrez votre carrière dès aujourd'hui
            </p>
            <a
              href="jobs.html"
              class="inline-block bg-black text-white rounded-lg px-4 py-2 hover:bg-gray-700"
            >
              Browse Jobs
            </a>
          </Card>
          <Card bg="bg-green-100">
            <h2 class="text-2xl font-bold">Pour les employeurs</h2>
            <p class="mt-2 mb-4">
              Répertoriez votre travail pour trouver le développeur idéal pour le poste
            </p>
            <a
              href="add-job.html"
              class="inline-block bg-green-500 text-white rounded-lg px-4 py-2 hover:bg-green-600"
            >
              Add Job
            </a>
          </Card>
        </div>
      </div>
    </section>

</template>


