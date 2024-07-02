<template>
    <section id="projects" class="py-16 bg-white">
      <div class="container mx-auto text-center">
        <h2 class="text-3xl font-bold mb-8 text-gray-800 custom-experiance">PROFESSIONAL EXPERIENCE AND INTERNSHIPS</h2>
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
          <div v-for="(project, index) in projects" :key="index" class="bg-white  p-8 rounded-lg shadow-md custom transform transition duration-300 hover:scale-105">
            <h3 class="text-3xl font-semibold mb-4 text-blue-600 text-name">{{ project.name }}</h3>
            <p class="text-lg text-gray-600 description" v-html="project.description"></p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
const projects = [
  { 
    name: '2023-2024', 
    description: `
      <p><strong>Frontend Developer at IOTHYS in Mauritius with INSYNIUM Company.</strong></p>
      <p><strong>Methods</strong>: PLM and SOLINGS</p>
      <p><strong>Technologies</strong>: Vue JS for Frontend, JAVA for Backend, THINGWORGS for API</p>
    `
  },
  { 
    name: '2022-2023', 
    description: `
      <p><strong>Developed a client space management application MYCPP for the CPP card in Madagascar.</strong></p>
      <p><strong>Technologies</strong>: Vue JS</p>
      <p><strong>Framework</strong>: Quasar for Frontend</p>
      <p><strong>Backend</strong>: Express JS</p>
    `
  },
  { 
    name: 'November 2022', 
    description: `
      <p><strong>Freelance project (CMS PROJECT)</strong></p>
      <p><strong>Frontend</strong>: React Material UI with Typescript using NEXTJS Framework</p>
      <p><strong>Backend</strong>: Python with AZURE FUNCTION</p>
    `
  },
  { 
    name: 'April 2022', 
    description: `
      <p><strong>Defended for International Certificate in English C2 from ITTI (International Tesol Training Institute), Madagascar.</strong></p>
    `
  },
  { 
    name: 'November 2021', 
    description: `
      <p><strong>Freelance project (International Salary Portage)</strong></p>
      <p>Frontend: Vue JS with Quasar Framework</p>
      <p>Backend: NEST JS</p>
    `
  },
  { 
    name: 'March 2020', 
    description: `
      <p><strong>Developed a banking management application at SAYNA using Laravel for Backend and Vue for Frontend</strong></p>
    `
  }
  // Add more projects as needed
];
</script>

  
  <style scoped>
  #projects{
    font-family: 'Roboto';
  }
  .custom{
     border: 0.02px solid rgb(236, 233, 233);
  }
  .custom-experiance{
    font-family: 'Roboto';
    font-size: 18px;
  }
  .description{
    font-family: 'Roboto';
    font-size: 14px;
  }
  </style>
  