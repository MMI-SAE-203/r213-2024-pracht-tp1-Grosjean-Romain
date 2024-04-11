<script setup lang="ts">
import { onErrorCaptured, ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
const sectionOpen = ref(1)
const menuIsOpen = ref(false)
</script>

<template>
  <h1 class="text-2xl">Accordéons</h1>
  <section>
  <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 1?0:1">bouton 1</button>
  <p v-show="sectionOpen === 1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam sit enim, eveniet quisquam officiis facilis aperiam est hic, aut perspiciatis, earum modi atque odio praesentium fuga nemo reprehenderit iure. Porro!</p>
</section>
<section>
  <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 2?0:2">bouton 2</button>
  <p v-show="sectionOpen === 2">Nam impedit optio maiores sint ratione fugit laborum consectetur, sed eaque in, voluptatibus aut nisi! Nostrum ut libero expedita enim quasi. Quidem, voluptatibus quasi voluptates corrupti dolorum odit suscipit sequi.</p>
</section>
<section>
  <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 3?0:3">bouton 3</button>
  <p v-show="sectionOpen === 3">Soluta nisi atque nemo magni id sunt sed deleniti cumque sequi? Laborum in, nobis repellendus ex iure ducimus blanditiis debitis voluptas odio qui neque a beatae excepturi itaque possimus! Error!</p>
</section>
</template>