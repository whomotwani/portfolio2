<template>
  <main class="container p-4 w-full md:w-3/4 mx-auto mb-28">
    <About class="mt-12" />

    <section class="mt-12">
      <p class="text-2xl mb-4">SKILLS</p>
      <div class="badge badge-primary mr-2" v-for="skill in data.skills" :key="skill">{{ skill }}</div>
    </section>

    <section class="mt-12">
      <p class="text-2xl mb-4">EXPERIENCES</p>
      <div class="flex flex-col gap-3 mb-10" v-for="experience in data.experiences" :key="experience.name">
        <div class="flex-1">
          <p class="text-xl">{{ experience.name }}, {{ experience.location }}</p>
          <p class="text-sm">{{ experience.startDate }} - {{ experience.endDate }}</p>
        </div>
        <div class="flex-1">
          <p class="mb-2">{{ experience.description }}</p>
          <div class="badge badge-primary badge-outline mr-2" v-for="skill in experience.skills" :key="skill">{{ skill
            }}</div>
        </div>
      </div>

      <div class="text-right">
        <button class="btn btn-neutral" @click="openResume">
          <span class="mr-1">View full resume</span>
          <span class="material-symbols-outlined text-sm">
            north_east
          </span>
        </button>
      </div>
    </section>

    <section class="mt-12">
      <p class="text-2xl mb-4">PROJECTS</p>
      <div class="flex flex-col gap-3 mb-10" v-for="project in data.projects" :key="project.name">
        <div class="flex-1">
          <a :href="project.link" target="_blank" class="text-xl">
            <span>
              {{ project.name }}
            </span>
            <span class="material-symbols-outlined text-sm ml-1">
              north_east
            </span>
          </a>
          <p class="text-sm">{{ project.startDate }} - {{ project.endDate }}</p>
        </div>
        <div class="flex-1">
          <p class="mb-2">{{ project.description }}</p>
          <div class="badge badge-primary badge-outline mr-2" v-for="skill in project.skills" :key="skill">{{ skill }}
          </div>
        </div>
      </div>
    </section>
  </main>
</template>
<script setup>
import data from './data.json'
import About from './components/About.vue';
function openResume() {
  const pdfPath = `${import.meta.env.BASE_URL}Resume.pdf`; // Access the file from the public folder
  window.open(pdfPath, '_blank'); // Opens the PDF in a new tab
}
</script>