<script setup lang="ts">
import { onErrorCaptured, ref } from 'vue'

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
const sectionsData = [
  {
    label: 'bouton 1',
    texte: `texte panneau 1 Lorem ipsum dolor sit ame
    consectetur adipisicing elit. Inventore animi dolore,
    rerum magni laudantium quod excepturi laboriosam, 
    ex modi debitis harum reprehenderit eaque quam ut
    ea molestiae. Id, cum dolor!`
  },
  {
    label: 'bouton 2',
    texte: `texte panneau 2 Amet alias provident quos quis, 
    Officia ut ab dolores quos dolorem accusamus ad,
    consectetur unde minima, ipsum eligendi inventore id
    labore, laborum rerum laboriosam corrupti iste.
    Distinctio, perspiciatis!`
  },
  {
    label: 'bouton 3',
    texte: `texte panneau 3 Repudiandae corporis voluptates, 
    odit reprehenderit sint pariatur at voluptatum, cumque
    quia sit eligendi ex culpa eos, alias magnam molestiae
    id modi accusantium ipsa eveniet accusamus. Tempora 
    quis corporis et nam.`
  }
]
const activeAccordeon = ref(0)
</script>

<template>
  <h1 class="text-2xl">Boucle sur des données</h1>
  <section v-for="({ label, texte }, key) of sectionsData" :key="key">
  <pre class="font-mono">key : {{ key }}</pre>
  <pre class="font-mono" @pointerdown="activeAccordeon = activeAccordeon === (key+1)?0:(key+1)">label : {{ label }}</pre>
  <pre class="font-mono" v-show ="activeAccordeon === (key+1)">texte : {{ texte }}</pre>
</section>
</template>