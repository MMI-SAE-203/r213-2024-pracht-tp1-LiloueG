<script setup lang="ts" >
import { onErrorCaptured } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'

import { ref } from 'vue'

const menuIsOpen = ref(false);

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
</script>

<template>
  <header>
    <button
    aria-controls="mainNav"
    aria-expanded="true"
    class="rounded-full border-2 border-red-600 bg-red-300 px-2"
    @pointerdown="menuIsOpen = !menuIsOpen">
    menu
    </button>
  <!-- nav#mainNav>ul>li*3>a[href="#"]{item $} -->
  <Transition
    class="transition-transform duration-1000"
    enter-from-class="-translate-x-full"
    enter-to-class="translate-x-0"
    leave-active-class="-translate-x-full"
  >
    <nav id="mainNav" v-show="menuIsOpen">
      <ul>
        <li><RouterLink to="/accordeon">Accordéon</RouterLink></li>
        <li><RouterLink to="/boucle_donnee">Boucle sur les données</RouterLink></li>
        <li><RouterLink to="#">item 3</RouterLink></li>
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
