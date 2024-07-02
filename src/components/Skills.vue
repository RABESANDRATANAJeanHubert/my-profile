<template>
  <div>
    <section class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12">
      <div class="text-center pb-12">
        <h1 class="font-bold text-3xl md:text-4xl lg:text-5xl font-heading text-gray-900 custom-text">
          SKILLS
        </h1>
      </div>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-6">
        <div
          v-for="(skill, index) in skills"
          :key="index"
          class="w-full bg-white rounded-lg p-6 flex flex-col justify-center items-center cursor-pointer shadow-md relative"
          @mouseenter="showFrameworks(index)"
          @mouseleave="hideFrameworks(index)"
          @click="openDialog(skill)"
        >
          <div class="mb-4">
            <img class="object-center object-cover rounded-full h-36 w-36" :src="`${skill.image}`" :alt="skill.name">
          </div>
          <div class="text-center">
            <p class="text-xl text-gray-700 font-bold mb-2 custom-name">{{ skill.name }}</p>
            <p class="text-base text-gray-400 font-normal custom-description" >   <button
                class="block w-full text-blue-800 text-sm font-semibold rounded-lg focus:outline-none focus:shadow-outline  hover:shadow-xs p-3 my-4">Show
                Show more detail ...</button></p>
          </div>
          <transition name="fade">
            <ul v-if="skill.showFrameworks" class="absolute bottom-0 left-0 right-0 bg-white rounded-b-lg p-2 shadow-md">
              <li v-for="(framework, idx) in skill.frameworks" :key="idx" class="text-sm text-gray-700">{{ framework }}</li>
            </ul>
          </transition>
        </div>
      </div>
    </section>

    <!-- Dialog Component -->
    <DialogSkills
      :show-dialog="showDialog"
      :selected-skill="selectedSkill"
      @close-dialog="closeDialog"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import DialogSkills from './DialogSkills.vue'; // Adjust the path as necessary

const skills = ref([
  {
    name: 'Programming Languages',
    description: 'Skilled in various programming languages such as JavaScript, Python, Java, etc.',
    image: 'langage.png', // Adjust the path to your actual asset location
    frameworks: ['Vue.js', 'React.js', 'Angular', 'Node.js'],
    showFrameworks: false, // Initially hide frameworks
  },
  {
    name: 'Frameworks',
    description: 'Skilled in frontend and backend frameworks like Vue.js, React.js, Express.js, etc.',
    image: 'framework.jpg', // Adjust the path to your actual asset location
    frameworks: ['Vue.js', 'React.js', 'Angular', 'Express.js'],
    showFrameworks: false, // Initially hide frameworks
  },
  {
    name: 'Web Technologies',
    description: 'Proficient in web technologies such as HTML5, CSS3, JavaScript, etc.',
    image: 'WebTechnologie.jpeg', // Adjust the path to your actual asset location
    frameworks: ['HTML5', 'CSS3', 'JavaScript','Tailwind', 'Bootstrap'],
    showFrameworks: false, // Initially hide frameworks
  },
  {
    name: 'Database Management Systems',
    description: 'Experienced in managing databases like MySQL, PostgreSQL, MongoDB, etc.',
    image: 'databaseManagement.jpg', // Adjust the path to your actual asset location
    frameworks: ['MySQL', 'PostgreSQL', 'MongoDB'],
    showFrameworks: false, // Initially hide frameworks
  },
  {
    name: 'Design Methodologies',
    description: 'Familiar with design methodologies such as Agile, Scrum, Waterfall, etc.',
    image: 'designMethodologie.jpg', // Adjust the path to your actual asset location
    frameworks: ['Agile', 'Scrum', 'Waterfall'],
    showFrameworks: false, // Initially hide frameworks
  },
  {
    name: 'Testing',
    description: 'Skilled in various testing methodologies and frameworks like Jest, Cypress, Selenium, etc.',
    image: 'testing.jpg', // Adjust the path to your actual asset location
    frameworks: ['Jest', 'Mocha', 'Selenium', 'Cypress'],
    showFrameworks: false, // Initially hide frameworks
  }
  // Add more skills as needed
]);

const showDialog = ref(false);
const selectedSkill = ref({});

const toggleFrameworks = (index) => {
  skills.value[index].showFrameworks = !skills.value[index].showFrameworks;
};

const openDialog = (skill) => {
  selectedSkill.value = skill;
  showDialog.value = true;
};

const closeDialog = () => {
  showDialog.value = false;
};
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0;
}
.custom-text {
    font-family: 'Roboto', sans-serif;
    font-size: 16px;
}
.custom-name{
    font-family: 'Roboto';
    font-size: 14px;
}
.custom-description{
    font-family: 'Roboto';
    font-size: 14px;
}
</style>
