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
  <header>
    <button
  aria-controls="mainNav"
  aria-expanded="true"
  class="rounded-full border-2 border-indigo-400 bg-indigo-300 px-8 text-white"
@pointerdown="menuIsOpen = !menuIsOpen">menu
</button>
<Transition
  class="transition-transform duration-1000"
  enter-from-class="-translate-x-full"
  enter-to-class="translate-x-0"
  leave-active-class="-translate-x-full"
>
<nav id="mainNav" v-show="menuIsOpen" class="full border-2 border-indigo-400 bg-indigo-300 px-2 text-white">
  <ul>
    <li><RouterLink to="/">Homepage</RouterLink></li>
    <li><RouterLink to="/accordeon">Lien vers Accordéon</RouterLink></li>
    <li><RouterLink to="/boucle">Lien vers Boucle sur des données</RouterLink></li>
  </ul>
</nav>
</Transition>
  </header>
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
