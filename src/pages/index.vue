<script setup lang="ts">
import { onErrorCaptured, ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})

const menuIsOpen = ref(false)
</script>

<template>
  <h1 class="text-2xl">Accordéons</h1>
  <section>
  <button class="text-xl">bouton 1</button>
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam sit enim, eveniet quisquam officiis facilis aperiam est hic, aut perspiciatis, earum modi atque odio praesentium fuga nemo reprehenderit iure. Porro!</p>
</section>
<section>
  <button class="text-xl">bouton 2</button>
  <p>Nam impedit optio maiores sint ratione fugit laborum consectetur, sed eaque in, voluptatibus aut nisi! Nostrum ut libero expedita enim quasi. Quidem, voluptatibus quasi voluptates corrupti dolorum odit suscipit sequi.</p>
</section>
<section>
  <button class="text-xl">bouton 3</button>
  <p>Soluta nisi atque nemo magni id sunt sed deleniti cumque sequi? Laborum in, nobis repellendus ex iure ducimus blanditiis debitis voluptas odio qui neque a beatae excepturi itaque possimus! Error!</p>
</section>
</template>
