<template>
  <div id="app">
    <HomePage />
  </div>
</template>

<script>
import HomePage from './components/HomePage.vue';

//import Header from './components/Header.vue';
//import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
   HomePage
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #000000;
  margin-top: 60px;
}
main {
  padding: 20px;
}
</style>