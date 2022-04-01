<template>
  <nav class="d-flex flex-row align-items p-20">
    <a @click="selectedComponant = 'PageA'" class="mr-10"> Page A </a>
    <a @click="selectedComponant = 'PageB'"> Page B </a>
  </nav>
  <div class="p-20">
    <Component :is="composants[selectedComponant]" />
  </div>
</template>

<script setup lang="ts">
import PageA from './PageA.vue';
import PageB from './PageB.vue';
import { ref, type Component as C } from 'vue';

const composants: { [s:string]: C } = {
  PageA,
  PageB,
};

const selectedComponant = ref('PageA');
</script>

<style lang="scss">
@import './assets/scss/base.scss';

nav {
  background-color: var(--primary-1);
  a {
    color: white;
  }
}
</style>
