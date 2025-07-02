<template>
  <section
      class="flex justify-center items-center dark:text-white min-h-screen mt-20 lg:mt-0"
  >
      <header
      class="absolute w-1/2 aspect-[16/5] -skew-x-12 rounded-full bg-gradient-to-r from-[#00c6cc]
      via-[#785ae4] to-secondary opacity-30 dark:opacity-20 blur[100p] left-10 top-0 hidden md:block"
  ></header>
  <header
      class="absolute w-1/2 aspect-[16/5] -skew-x-12 rounded-full bg-gradient-to-r from-[#00c6cc]
      via-[#785ae4] to-secondary opacity-30 dark:opacity-20 blur[100p] right-10 bottom-0 hidden md:block"
  ></header>
  <main class="absolute grid lg:grid-cols-2 grid-cols-1 items-center p-2 lg:p-8">
      <header class="text-center lg:text-left">
          <h1 class="mb-6 text-4xl md:text-5xl lg:text-6xl font-bold">
              Hi, I'm 
              <span class="relative px-2 font-extrabold text-black dark:text-white">Syamir</span>
          </h1>
          <p class="mb-8 text-lg md:text-xl max-w-xl mx-auto lg:mx-0 font-sans-pro text-gray-900 dark:text-gray-100 transition-colors duration-500">
            I am a passionate frontend developer with a love for crafting beautiful and functional web experiences. With a strong background in modern JavaScript frameworks and a keen eye for design, I strive to deliver high-quality solutions that delight users and drive results.
          </p>
          <p class="mb-8 text-lg md:text-xl max-w-xl mx-auto lg:mx-0 font-sans-pro text-gray-700 dark:text-gray-300 transition-colors duration-500">
            As the youngest of six siblings, I chose not to pursue a degree in IT after my studies were cut short due to financial constraints. Determined to remain debt free and avoid student loans, I am now focused on leveraging my diploma to secure a role in the IT industry. My resilience and practical mindset in overcoming challenges reflect my readiness to contribute meaningfully to any organization.
          </p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
            <a href="https://bobamilkutea.github.io/resume1/SyamirNorzalimi.pdf" target="_blank" rel="noopener" class="px-8 py-3 rounded-full font-semibold border-2 border-yellow-400 bg-yellow-400 text-black hover:bg-transparent hover:text-yellow-400 transition flex items-center gap-2 font-sans-pro">
              <span class="material-icons"></span> View Resume
            </a>
            <a href="https://bobamilkutea.github.io/syamircv/CVSyamir.pdf" target="_blank" rel="noopener" class="px-8 py-3 rounded-full font-semibold border-2 border-yellow-400 bg-yellow-400 text-black hover:bg-transparent hover:text-yellow-400 transition flex items-center gap-2 font-sans-pro">
              <span class="material-icons"></span> View CV
            </a>
            <button @click="$emit('scrollToContact')" class="px-8 py-3 rounded-full font-semibold border-2 border-yellow-400 text-yellow-400 hover:bg-yellow-400 hover:text-black transition font-sans-pro">
              Hire Me
            </button>
          </div>
      </header>
      <div class="flex justify-center lg:justify-end mt-8 lg:mt-0">
        <img src="@/assets/IMG_9233.jpg" alt="Profile" class="w-56 h-56 object-cover rounded-full border-4 border-yellow-400 shadow-lg profile-img" />
      </div>
  </main>
  </section>
  <!-- Skills Section -->
  <section id="skills" class="w-full py-16 bg-gradient-to-b from-transparent to-blue-100 dark:to-[#080326]">
    <h2 class="text-center text-4xl font-bold mb-12 text-gray-800 dark:text-white">My Skills</h2>
    <div class="flex flex-wrap justify-center gap-6 max-w-5xl mx-auto">
      <div v-for="(skill, idx) in skills" :key="skill.name" class="bg-[#0E2148] dark:bg-[#0E2148] rounded-xl shadow-lg p-6 w-40 flex flex-col items-center transition-colors duration-500">
        <span class="text-3xl font-bold text-white mb-2">
          {{ animatedPercents[idx] }}%
        </span>
        <span class="text-lg font-semibold text-yellow-300 mb-1">{{ skill.name }}</span>
      </div>
    </div>
  </section>
  <!-- Traits Section -->
  <section id="traits" class="w-full py-16 bg-gradient-to-b from-transparent to-blue-50 dark:to-[#0E2148]">
    <h2 class="text-center text-4xl font-bold mb-12 text-gray-800 dark:text-white font-sans-pro">Traits</h2>
    <div class="flex flex-wrap justify-center gap-6 max-w-5xl mx-auto">
      <div class="bg-[#0E2148] dark:bg-[#0E2148] rounded-xl shadow-lg p-6 w-72 flex flex-col items-center transition-colors duration-500">
        <span class="text-2xl font-bold text-yellow-300 mb-2 font-sans-pro">Fast Learner</span>
        <span class="text-base text-white text-center font-sans-pro">I quickly adapt to new technologies and environments, ensuring a smooth and efficient learning process in any situation.</span>
      </div>
      <div class="bg-[#0E2148] dark:bg-[#0E2148] rounded-xl shadow-lg p-6 w-72 flex flex-col items-center transition-colors duration-500">
        <span class="text-2xl font-bold text-yellow-300 mb-2 font-sans-pro">Critical Thinker</span>
        <span class="text-base text-white text-center font-sans-pro">I approach problems analytically and creatively, consistently finding effective solutions to complex challenges.</span>
      </div>
      <div class="bg-[#0E2148] dark:bg-[#0E2148] rounded-xl shadow-lg p-6 w-72 flex flex-col items-center transition-colors duration-500">
        <span class="text-2xl font-bold text-yellow-300 mb-2 font-sans-pro">Communication</span>
        <span class="text-base text-white text-center font-sans-pro">I foster an environment where everyone feels empowered and respected. Through active listening, clear communication, and a commitment to collective growth, I help teams thrive and achieve excellence together.</span>
      </div>
    </div>
  </section>
  <!-- Why Me Section -->
  <section id="whyme" class="w-full py-16 bg-gradient-to-b from-blue-100 to-transparent dark:from-[#080326] dark:to-transparent">
    <h2 class="text-center text-4xl font-bold mb-12 text-gray-800 dark:text-white">Why Me?</h2>
    <div class="max-w-5xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-10">
      <!-- Education -->
      <div>
        <h3 class="text-2xl font-bold mb-6 text-center text-gray-800 dark:text-white">Education</h3>
        <div class="space-y-6">
          <div class="bg-[#0E2148] dark:bg-[#0E2148] rounded-xl shadow-lg p-6 flex items-center gap-4">
            <span class="material-icons text-yellow-400 text-4xl">school</span>
            <div>
              <div class="font-bold text-yellow-300">KPTM</div>
              <div class="text-white text-sm">KPTM Batu Pahat</div>
              <div class="text-white text-sm">Diploma in Information Technology</div>
              <div class="text-gray-400 text-xs">11/2022 - 04/2025</div>
            </div>
          </div>
          <div class="bg-[#0E2148] dark:bg-[#0E2148] rounded-xl shadow-lg p-6 flex items-center gap-4">
            <span class="material-icons text-yellow-400 text-4xl">school</span>
            <div>
              <div class="font-bold text-yellow-300">SMKDH</div>
              <div class="text-white text-sm">Sekolah Menengah kebangsaan Dato Hamzah</div>
              <div class="text-white text-sm">Pure Science</div>
              <div class="text-gray-400 text-xs">2017-2021</div>
            </div>
          </div>
        </div>
      </div>
      <!-- Experience -->
      <div>
        <h3 class="text-2xl font-bold mb-6 text-center text-gray-800 dark:text-white">Experience</h3>
        <div class="space-y-6">
          <div class="bg-[#0E2148] dark:bg-[#0E2148] rounded-xl shadow-lg p-6 flex items-center gap-4">
            <span class="material-icons text-yellow-400 text-4xl">work</span>
            <div>
              <div class="font-bold text-yellow-300">Intern</div>
              <div class="text-white text-sm">Modern Workspace Analyst</div>
              <div class="text-white text-sm">Logicalis</div>
              <div class="text-gray-400 text-xs">12/2024 - 05/2025</div>
            </div>
          </div>
          <div class="bg-[#0E2148] dark:bg-[#0E2148] rounded-xl shadow-lg p-6 flex items-center gap-4">
            <span class="material-icons text-yellow-400 text-4xl">work</span>
            <div>
              <div class="font-bold text-yellow-300">Part time</div>
              <div class="text-white text-sm">Retail Associate</div>
              <div class="text-white text-sm">Uniqlo</div>
              <div class="text-gray-400 text-xs">07/2022 - 10/2022</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- Contact Me Section -->
  <section id="contact" class="w-full py-16 bg-gradient-to-b from-transparent to-blue-200 dark:to-[#0E2148]">
    <h2 class="text-center text-4xl font-bold mb-6 text-gray-800 dark:text-white">Contact Me</h2>
    <p class="text-center max-w-2xl mx-auto mb-8 text-lg text-gray-700 dark:text-gray-300 transition-colors duration-500">
      If you'd like to get in touch with me, please feel free to reach out at any time. Whether you have questions, need assistance, or simply want to share your thoughts, I'm here to listen and help. Your input is valuable, and I'm committed to providing the support and guidance you need. Contact me, and let's start the conversation.
    </p>
    <div class="flex flex-col md:flex-row justify-center items-center gap-8 bg-white/10 dark:bg-[#0E2148]/80 rounded-xl p-8 max-w-3xl mx-auto">
      <div class="flex flex-col gap-2 text-center md:text-left">
        <div><span class="font-bold">📞 Phone Number :</span> <a href="tel:0176652691" class="text-blue-400 hover:underline">017-6652-691</a></div>
        <div><span class="font-bold">💼 Linkedin :</span> <a href="https://www.linkedin.com/in/syamir-norzalimi-1785392b4/" class="text-blue-400 hover:underline">Syamir Norzalimi</a></div>
      </div>
      <div class="flex flex-col gap-2 text-center md:text-left">
        <div><span class="font-bold">✉️ Email :</span> <a href="mailto:Syamir.dream@gmail.com" class="text-blue-400 hover:underline">Syamir.dream@gmail.com</a></div>
        <div><span class="font-bold">🐙 GitHub :</span> <a href="https://github.com/bobamilkutea" class="text-blue-400 hover:underline">bobamilkutea</a></div>
      </div>
    </div>
  </section>
</template>
<script setup>
import { ref, onMounted } from 'vue'
const skills = [
{ name: 'HTML', percent: 90 },
{ name: 'Figma', percent: 60 },
{ name: 'Java', percent: 92 },
{ name: 'Vue js', percent: 72 },
{ name: 'Wordpress', percent: 50 },
{ name: 'C#', percent: 60 },
{ name: 'ReactJS', percent: 70 },
{ name: 'Javascript', percent: 90 },
];

// Animated skill percentages
const animatedPercents = ref(skills.map(() => 0));
onMounted(() => {
skills.forEach((skill, idx) => {
  let start = 0;
  const end = skill.percent;
  const duration = 1200; // ms
  const stepTime = Math.max(Math.floor(duration / end), 10);
  const interval = setInterval(() => {
    if (animatedPercents.value[idx] < end) {
      animatedPercents.value[idx]++;
    } else {
      clearInterval(interval);
    }
  }, stepTime);
});
});
</script>

<style scoped>
/* Smooth transition for color/background changes */
.bg-\[\#0E2148\], .dark\:bg-\[\#0E2148\], .rounded-xl, .shadow-lg, .text-white, .text-black, .text-yellow-300, .text-gray-800, .dark\:text-white, .dark\:text-gray-300, .bg-yellow-400, .hover\:bg-transparent, .hover\:text-yellow-400 {
transition: background-color 0.5s, color 0.5s;
}
.font-sans-pro {
font-family: 'Inter', 'Lato', 'Nunito Sans', Arial, Helvetica, sans-serif;
letter-spacing: 0.01em;
}
.profile-img {
object-position: center top;
}
</style>
