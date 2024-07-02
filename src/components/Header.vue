<template>
  <header class="from-blue-500 to-indigo-600 text-black p-6 w-full top-0 z-50 header">
    <nav class="container mx-auto flex justify-between items-center">
      <h1 class="text-3xl font-bold">My Portfolio</h1>
      <ul class="flex space-x-6">
        <li>
          <a
            href="#contact"
            :class="['link', { active: activeLink === '#contact' }]"
            @click.prevent="handleClick('#contact')"
          >Information</a>
        </li>
        <li>
          <a
            href="#skills"
            :class="['link', { active: activeLink === '#skills' }]"
            @click.prevent="handleClick('#skills')"
          >Skills</a>
        </li>

        <li>
          <a
            href="#projects"
            :class="['link', { active: activeLink === '#projects' }]"
            @click.prevent="handleClick('#projects')"
          >Experiance</a>
        </li>
        <li>
          <a
            href="#about"
            :class="['link', { active: activeLink === '#about' }]"
            @click.prevent="handleClick('#about')"
          >Follows</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue';

const activeLink = ref('#about')

const handleClick = (target) => {
  activeLink.value = target
  scrollToElement(target, 0)
};

const scrollToElement = (target, delay) => {
  setTimeout(() => {
    const element = document.querySelector(target)
    if (element) {
      window.scrollTo({
        top: element.offsetTop,
        behavior: 'smooth',
      })
    }
  }, delay)
};
</script>

<style scoped>
.header {
  border: 1px solid rgba(63, 7, 7, 0.3);
  border-radius: 8px;
  font-family: 'Roboto',sans-serif;
}

.link {
  padding: 0.5rem 1rem;
  border: 2px solid transparent;
  border-radius: 4px;
  transition: all 0.3s ease;
}

.link:hover,
.link.active {
  border-color: rgba(255, 255, 255, 0.6);
  background-color: rgba(255, 255, 255, 0.1);
  text-decoration: none;
  animation: hoverAnimation 0.3s forwards;
  border: 1px solid rgb(55, 55, 209);
}

@keyframes hoverAnimation {
  from {
    transform: scale(1);
  }
  to {
    transform: scale(1.1);
  }
}
</style>
