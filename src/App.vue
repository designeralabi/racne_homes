<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HeaderBanner from '@/components/HeaderBanner.vue'
</script>

<template>
  <header class="z-40">
    <HeaderBanner />
    <main class="bg-black text-white">
      <nav class="container mx-auto px-24 py-7 flex items-center justify-between">
        <div class="text-xl">Racnehomes</div>
        <!-- navlinks -->
        <div class="flex w-[514px] justify-between items-center">
          <RouterLink to="/">Home</RouterLink>
          <RouterLink class="relative" to="/about"
            >About
            <ul
              class="group-hover absolute top-12 w-[200px] flex-col z-30 bg-red-600 px-8 py-6 space-y-6 hidden"
            >
              <RouterLink class="" to="/about">Who we are</RouterLink>
              <RouterLink to="/about">What we do</RouterLink>
              <RouterLink to="/about">Vision & Mission</RouterLink>
              <RouterLink to="/about">Portfolio</RouterLink>
              <RouterLink to="/about">Our team</RouterLink>
            </ul>
          </RouterLink>

          <RouterLink to="/about">About</RouterLink>
          <RouterLink to="/about">About</RouterLink>
          <h3
            class="bg-red-600 ease-in-out transition-all hover:bg-red-700 rounded-full cursor-pointer px-8 py-2 capitalize font-bold"
          >
            get in touch
          </h3>
        </div>
      </nav>
    </main>
  </header>

  <RouterView />
</template>

<!-- <style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style> -->
