<template>
    <header>
      <nav>
        <router-link to="/">Accueil</router-link> |
    <router-link to="/conversations">Conversations</router-link>
      </nav>
    </header>
  </template>
  
  <script>
  export default {
    name: 'AppHeader'
  }
  </script>
  
  <style scoped>
  header {
    background-color: #6b17a3;
    color: white;
    padding: 15px;
  }
  nav ul {
    list-style-type: none;
    padding: 0;
  }
  nav ul li {
    display: inline;
    margin: 0 15px;
  }
  nav ul li a {
    color: white;
    text-decoration: none;
  }
  </style>