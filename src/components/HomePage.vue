<template>
    <div>
      <h2>Welcome to the Home Page!</h2>
      <BaseButton :isDisabled="false">Click Me!</BaseButton>
      <BaseButton :isDisabled="true">Disabled Button</BaseButton>
    </div>
  </template>
  
  <script>
  import BaseButton from './BaseButton.vue';
  
  export default {
    name: 'HomePage',
    components: {
      BaseButton
    }
  }
  </script>
  
  <style scoped>
  /* Add additional styles for HomePage if needed */
  </style>