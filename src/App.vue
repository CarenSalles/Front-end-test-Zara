<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HomeView from './views/HomeView.vue';


</script>

<template>

<RouterLink to="/">Home</RouterLink>
        
  <RouterView /> 

  <HomeView />
  
</template>

<style scoped>

</style>
