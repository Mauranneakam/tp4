<template>
  <div id="app">
    <Header />
    <HomePage />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import HomePage from './components/HomePage.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    HomePage
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
main {
  padding: 20px;
  margin-bottom: 60px; /* To avoid overlap with the footer */
}
</style>