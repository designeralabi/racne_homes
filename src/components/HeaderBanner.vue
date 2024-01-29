<template>
  <div
    class="text-white text-sm flex items-center justify-center py-2"
    :style="{ background: 'red' }"
  >
    welcome to racneHomes, Contact us Now: 08069171876, 08085808285
    <!-- social handles -->
    <div class="flex items-center text-xl space-x-4 ml-3">
      <a href="#">
        <FaBandsFacebook />
      </a>
      <a href="#">
        <AkInstagramFill />
      </a>
      <a href="#">
        <AkTwitterFill />
      </a>
      <a href="#">
        <AkLinkedinBoxFill />
      </a>
    </div>
  </div>
</template>

<script setup>
import { FaBandsFacebook } from '@kalimahapps/vue-icons'
import { AkInstagramFill } from '@kalimahapps/vue-icons'
import { AkTwitterFill } from '@kalimahapps/vue-icons'
import { AkLinkedinBoxFill } from '@kalimahapps/vue-icons'
</script>
