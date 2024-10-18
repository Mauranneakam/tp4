<template>
    <div id="base-layout">
      <Header />
      <main>
        <slot></slot>
      </main>
      <Footer />
    </div>
  </template>
  
  <script>
  import Header from './Header.vue';
  import Footer from './Footer.vue';
  
  export default {
    name: 'BaseLayout',
    components: {
      Header,
      Footer
    }
  }
  </script>
  
  <style scoped>
  #base-layout {
    display: flex;
    flex-direction: column;
    min-height: 100vh; /* Ensure the layout takes full height */
  }
  main {
    flex: 1; /* Allow main content to grow */
    padding: 20px;
  }
  </style>