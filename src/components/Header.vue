<template>
    <header>
      <nav>
        <ul>
          <li><a href="#">Home</a></li>
          <li><span>Mau</span></li>
        </ul>
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
    background-color: #35495e;
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