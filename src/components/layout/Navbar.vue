<template>
  <header class="w-full fixed top-0 left-0 z-50">
    <div class="flex justify-between items-center px-6 py-4 lg:px-12 backdrop-blur-md bg-transparent">
      <!-- Logo -->
      <div class="text-4xl font-bold dark:text-white text-primary"></div>

      <!-- Toggle button (mobile) -->
      <div class="md:hidden">
        <button @click="isMenuOpen = !isMenuOpen" class="text-white text-4xl z-50 relative">
          <Icon :icon="isMenuOpen ? 'material-symbols:close' : 'material-symbols:menu'" />
        </button>
      </div>

      <!-- Navbar links (desktop) -->
      <ul class="hidden md:flex md:items-center md:space-x-10 font-bold text-2xl"
          :class="isDarkMode ? 'text-white' : 'text-primary'">
        <li v-for="item in Menu" :key="item.name">
          <a
            :href="item.href"
            @click.prevent="scrollToSection(item.href)"
            class="hover:text-secondary transition"
          >
            {{ item.name }}
          </a>
        </li>

        <!-- Dark Mode Toggle -->
        <button @click="toggleDarkMode" class="ml-6 group relative overflow-hidden">
          <span class="inline-block transition-transform duration-500 group-hover:rotate-180">
            <Icon
              :icon="isDarkMode ? 'line-md:sunny-outline' : 'line-md:moon-filled'"
              class="text-4xl hover:text-secondary"
            />
          </span>
        </button>
      </ul>
    </div>

    <!-- Mobile menu -->
    <div
      v-if="isMenuOpen"
      class="fixed inset-0 bg-primary bg-opacity-95 flex flex-col items-center justify-center space-y-8 md:hidden z-40"
    >
      <ul :class="isDarkMode ? 'text-white' : 'text-primary'">
        <li v-for="item in Menu" :key="item.name">
          <a
            :href="item.href"
            @click.prevent="scrollToSection(item.href)"
            class="text-3xl font-semibold hover:text-secondary"
          >
            {{ item.name }}
          </a>
        </li>
      </ul>
      <button @click="toggleDarkMode" class="group relative overflow-hidden">
        <span class="inline-block transition-transform duration-500 group-hover:rotate-180">
          <Icon
            :icon="isDarkMode ? 'line-md:sunny-outline' : 'line-md:moon-filled'"
            class="text-4xl hover:text-secondary"
          />
        </span>
      </button>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { Icon } from '@iconify/vue'

const isMenuOpen = ref(false)

const Menu = ref([
  { name: 'Skills', href: '#skills' },
  { name: 'Traits', href: '#traits' },
  { name: 'Why Me', href: '#whyme' },
  { name: 'Projects', href: '#projects' },
  { name: 'Contact', href: '#contact' }
])

const scrollToSection = (href) => {
  isMenuOpen.value = false
  const section = document.querySelector(href)
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' })
  }
}

const isDarkMode = ref(false)

const toggleDarkMode = () => {
  const html = document.documentElement
  if (isDarkMode.value) {
    html.classList.remove('dark')
    localStorage.setItem('theme', 'light')
  } else {
    html.classList.add('dark')
    localStorage.setItem('theme', 'dark')
  }
  isDarkMode.value = !isDarkMode.value
}

onMounted(() => {
  const savedTheme = localStorage.getItem('theme')
  if (savedTheme === 'dark') {
    document.documentElement.classList.add('dark')
    isDarkMode.value = true
  }
})
</script>

<style scoped>
.bg-primary {
  background-color: #0E2148;
}
.text-secondary {
  color: #E3D095;
}
/* Sun/Moon morph animation */
.group:hover .inline-block {
  transform: rotate(180deg) scale(1.1);
  transition: transform 0.5s cubic-bezier(0.4,0,0.2,1);
}
</style>
