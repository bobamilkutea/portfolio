<template>
  <div class="bg-[#D4EBF8] dark:bg-[#080326] min-h-screen">
    <Navbar />
    <HeroSection @scrollToContact="scrollToContact" />
  </div>
</template>

<script setup>
import {defineAsyncComponent} from 'vue';
const Navbar = defineAsyncComponent(() => import('./components/layout/Navbar.vue'));
const HeroSection = defineAsyncComponent(() => import('./components/layout/HeroSection.vue'));

function scrollToContact() {
  const section = document.querySelector('#contact');
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' });
  }
}
</script>

