<template>
  <v-app>
    <header class="d-flex flex-column">
      <default-bar />
    </header>
    <default-view />
    <Footer />
  </v-app>
</template>

<script setup>
  import DefaultBar from './AppBar.vue'
  import DefaultView from './View.vue'
  import Footer from "./Footer.vue";
</script>
