<template>
  <div class="px-52 py-24 bg-white">
    <div class="flex justify-between">
      <div class="text-xl flex flex-col items-center">
        <img :src="racneLogo" alt="racne_logo" class="w-24" />
        <h3>Racnehomes</h3>
      </div>
      <!-- links -->
      <div>
        <ul class="flex flex-col space-y-3">
          <!-- <RouterLink class="" to="/about">Who we are</RouterLink> -->
          <li>
            <RouterLink to="/about">What we do</RouterLink>
          </li>
          <li><RouterLink to="/about">Vision & Mission</RouterLink></li>
          <li><RouterLink to="/about">Portfolio</RouterLink></li>
          <li><RouterLink to="/about">Our team</RouterLink></li>
        </ul>
      </div>
      <!-- address -->
      <div>
        <div>
          <h3>Lagos</h3>
          <p class="mt-2">
            151 Herbert Macaulay Way, <br />
            Yaba, Lagos, Nigeria
          </p>
        </div>
        <div class="mt-3">
          <h3>Ibadan</h3>
          <p class="mt-2">
            91 Wimpole Street, London <br />
            W1G 0EF UK
          </p>
        </div>
      </div>
    </div>

    <div class="flex mt-14 text-gray-600 items-center justify-between">
      <h3>Terms & conditions</h3>
      <h3>&copy;{{ nowDate.getFullYear() }} racnehomes all Rights Reserved</h3>
      <h3>developed by devlab❤️</h3>
    </div>
  </div>
</template>

<script setup>
import racneLogo from '../assets/racne_logo.png'
import { ref } from 'vue'
const nowDate = ref(new Date())
// const colorRed = ref('colorRed')
</script>

<style scoped>
/* .colorRed {
//   background-color: red;
// } */

li:hover {
  color: red;
}
</style>
