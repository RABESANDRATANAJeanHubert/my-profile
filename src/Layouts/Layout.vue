<template>
  <div id="app">
    <Header />
    <main>
      <section id="contact" class="section">
        <Contact />
      </section>
      <section id="projects" class="section">
        <Projects />
      </section>
      <section id="skills" class="section">
        <Skills />
      </section>
      <section id="about" class="section">
        <About />
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import Contact from '../components/Contact.vue';
import Header from '../components/Header.vue';
import About from '../components/About.vue';
import Projects from '../components/Projects.vue';
import Skills from '../components/Skills.vue';

const activeSection = ref('')

onMounted(() => {
  checkActiveSection()
  window.addEventListener('scroll', checkActiveSection);
});

const checkActiveSection = () => {
  const sections = document.querySelectorAll('.section')
  sections.forEach(section => {
    const sectionTop = section.offsetTop - 100
    const sectionId = section.getAttribute('id')
    const scrollPosition = window.scrollY;
    if (scrollPosition >= sectionTop) {
      activeSection.value = sectionId;
    }
  })
}
</script>

<style>
body {
  margin: 0;
  font-family: var(--font-family);
}

main {
  margin-top: 80px;
}
#header-navigation a {
  color: #333;
  text-decoration: none;
  transition: color 0.3s ease;
}

#header-navigation a.active {
  color: var(--header-navigation-color);
}
</style>
