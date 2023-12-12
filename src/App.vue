<script setup>
import NavBar from './components/NavBar.vue'
import HomePage from './components/HomePage.vue'
//import LoadingScreen from './components/LoadingScreen.vue';
import { ref, onMounted } from 'vue';

const isLoading = ref(true);

onMounted(() => {
  setTimeout(() => {
    isLoading.value = false;
  }, 1000);
});

</script>

<template>

  <!--<LoadingScreen v-if="isLoading"/>-->
  <NavBar />
  <HomePage />
  
</template>

<style>

body {
  min-height: 100vh;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: rgb(21, 21, 21);
  color:rgb(246, 246, 233);
  font-family:
    Inter,
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    Oxygen,
    Ubuntu,
    Cantarell,
    'Fira Sans',
    'Droid Sans',
    'Helvetica Neue',
    sans-serif;
  transition:
    color 0.5s,
    background-color 0.5s;
}

</style>
