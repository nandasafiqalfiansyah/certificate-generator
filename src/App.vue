<script setup lang="ts">
import Index from './components/Index.vue'
import Navbar from './components/navbar.vue'
</script>

<template>
  <v-app>
    <Navbar/>
    <Index />
  </v-app>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
