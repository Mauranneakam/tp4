<template>
  <div id="app">
    <BaseLayout>
      <template #main>
        <HomePage :user="user" @user-signed-in="setUser" />
      </template>
    </BaseLayout>
  </div>
</template>

<script>
//import Header from './components/Header.vue';
//import Footer from './components/Footer.vue';
import HomePage from './components/HomePage.vue';
import BaseLayout from './components/BaseLayout.vue';

export default {
  name: 'App',
  components: {
    BaseLayout,
    HomePage
  },
  data() {
    return {
      user: null // Store the user information here
    };
  },
  methods: {
    setUser(user) {
      this.user = user; // Update the user with the received information
    }
}
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #000203;
  margin-top: 60px;
}
main {
  padding: 20px;
  margin-bottom: 60px; /* To avoid overlap with the footer */
}
</style>