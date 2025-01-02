<script setup>

</script>
<template>

  <section class="bg-green-50">
    <div class="container m-auto px-6 py-10">
      <div class="gridcols grid w-full grid-cols-1 gap-6 md:grid-cols-2">
        <main class="">
          <div class="rounded-lg bg-white p-6 text-center shadow-md md:text-left">
            <div class="mb-4 text-gray-500">Full-Time</div>
            <h1 class="mb-4 text-3xl font-bold">Senior Vue Developer</h1>
            <div class="mb-4 flex justify-center align-middle text-gray-500 md:justify-start">
              <i class="fa-solid fa-location-dot mr-2 text-lg text-orange-700"></i>
              <p class="text-orange-700">Boston, MA</p>
            </div>
          </div>

          <div class="mt-6 rounded-lg bg-white p-6 shadow-md">
            <h3 class="mb-6 text-lg font-bold text-green-800">
              Job Description
            </h3>

            <p class="mb-4">
              We are seeking a talented Front-End Developer to join our team
              in Boston, MA. The ideal candidate will have strong skills in
              HTML, CSS, and JavaScript, with experience working with modern
              JavaScript frameworks such as Vue or Angular.
            </p>

            <h3 class="mb-2 text-lg font-bold text-green-800">Salary</h3>

            <p class="mb-4">$70k - $80K / Year</p>
          </div>
        </main>

        <!-- Sidebar -->
        <aside class="">
          <!-- Company Info -->
          <div class="rounded-lg bg-white p-6 shadow-md">
            <h3 class="mb-6 text-xl font-bold">Company Info</h3>

            <h2 class="text-2xl">NewTek Solutions</h2>

            <p class="my-2">
              NewTek Solutions is a leading technology company specializing in
              web development and digital solutions. We pride ourselves on
              delivering high-quality products and services to our clients
              while fostering a collaborative and innovative work environment.
            </p>

            <hr class="my-4" />

            <h3 class="text-xl">Contact Email:</h3>

            <p class="my-2 bg-green-100 p-2 font-bold">
              contact@newteksolutions.com
            </p>

            <h3 class="text-xl">Contact Phone:</h3>

            <p class="my-2 bg-green-100 p-2 font-bold">555-555-5555</p>
          </div>

          <!-- Manage -->
          <div class="mt-6 rounded-lg bg-white p-6 shadow-md">
            <h3 class="mb-6 text-xl font-bold">Manage Job</h3>
            <a href="add-job.html"
              class="focus:shadow-outline mt-4 block w-full rounded-full bg-green-500 px-4 py-2 text-center font-bold text-white hover:bg-green-600 focus:outline-none">Edit
              Job</a>
            <button
              class="focus:shadow-outline mt-4 block w-full rounded-full bg-red-500 px-4 py-2 font-bold text-white hover:bg-red-600 focus:outline-none">
              Delete Job
            </button>
          </div>
        </aside>
      </div>
    </div>
  </section>
</template>
<style lang="css" scoped>
  @media (min-width: 768px) {
  .gridcols {
    grid-template-columns: 70% 30%;
  }
}
</style>
