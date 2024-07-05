<template>
    <section id="projects" class="py-16 bg-white">
      <div class="container mx-auto text-center">
        <h2 class="text-3xl font-bold mb-8 text-gray-800 custom-experiance">PROFESSIONAL EXPERIENCE AND INTERNSHIPS</h2>
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
          <div v-for="(project, index) in experiences" :key="index" class="bg-white  p-8 rounded-lg shadow-md custom transform transition duration-300 hover:scale-105">
            <h3 class="text-3xl font-semibold mb-4 text-blue-600 text-name">{{ project.name }}</h3>
            <p class="text-lg text-gray-600 description" v-html="project.description"></p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
import {experiences} from '../models'
</script>

  
  <style scoped>
  #projects{
    font-family: var(--font-family);
  }
  .custom{
     border: 0.02px solid rgb(236, 233, 233);
  }
  .custom-experiance{
    font-family: var(--font-family);
    font-size: 18px;
  }
  .description{
    font-family: var(--font-family);
    font-size: var(--font-size);
  }
  </style>
  