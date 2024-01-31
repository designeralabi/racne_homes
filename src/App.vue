<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HeaderBanner from '@/components/HeaderBanner.vue'
import racneLogo from './assets/racne_logo.png'
import { AkChevronDown } from '@kalimahapps/vue-icons'
import { ref } from 'vue'
const mainBtn = ref('mainBtn')
const nestedMenu = ref(false)
function toggleAbout() {
  nestedMenu.value = !nestedMenu.value
  console.log('toggle button clicked')
}

// import FooterNavVue from './components/FooterNav.vue'
</script>

<template>
  <header class="z-40">
    <HeaderBanner />
    <main class="bg-black text-white">
      <nav class="container mx-auto px-24 py-7 flex items-center justify-between">
        <div class="text-xl flex items-center">
          <img :src="racneLogo" alt="racne_logo" class="w-24" />
          <h3>Racnehomes</h3>
        </div>
        <!-- navlinks -->
        <div class="flex w-[514px] justify-between items-center">
          <RouterLink to="/">Home</RouterLink>
          <RouterLink class="relative" to="/about">
            About
            <AkChevronDown
              @click="toggleAbout"
              class="text-white text-lg absolute right-0 -translate-y-5 translate-x-6"
            />
            <ul
              class="group-hover flex absolute top-12 w-[200px] flex-col z-30 bg-red-600 px-8 py-6 space-y-6 transition"
              :class="nestedMenu ? 'block' : 'hidden'"
            >
              <RouterLink class="" to="/about">Who we are</RouterLink>
              <RouterLink to="/about">What we do</RouterLink>
              <RouterLink to="/about">Vision & Mission</RouterLink>
              <RouterLink to="/about">Portfolio</RouterLink>
              <RouterLink to="/about">Our team</RouterLink>
            </ul></RouterLink
          >

          <RouterLink to="/about">Properties</RouterLink>
          <RouterLink to="/about">Blog</RouterLink>
          <h3 class="capitalize font-bold" :class="mainBtn">Contact us</h3>
        </div>
      </nav>
    </main>
  </header>

  <RouterView />
</template>

<style scoped>
.mainBtn {
  background-color: red;
  padding: 10px 40px;
  border-radius: 8px;
  color: whitesmoke;
  cursor: pointer;
  transition: all 1s ease-in-out;
}

.mainBtn:hover {
  background-color: rgb(214, 0, 0);
}
</style>
