<template>
  <div id="app">
    <Header />
    <main>
      <h1>Welcome to Vue OAuth Microsoft Graph!</h1>
      <p>Your application content goes here.</p>
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer
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