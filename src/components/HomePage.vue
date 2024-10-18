<template>
    <div>
      <h2>Welcome to the Home Page!</h2>
      <BaseButton color="primary" :isDisabled="false">Primary Button</BaseButton>
      <BaseButton color="warn" :isDisabled="false">Warn Button</BaseButton>
      <BaseButton color="danger" :isDisabled="false">Danger Button</BaseButton>
      <BaseButton color="danger" :isDisabled="true">Disabled Danger Button</BaseButton>
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