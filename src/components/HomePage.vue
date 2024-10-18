<template>
  <div>
    <h2>Welcome to the Home Page!</h2>
    <BaseButton color="primary" :isDisabled="false">Primary Button</BaseButton>
    <BaseButton color="warn" :isDisabled="false">Warn Button</BaseButton>
    <BaseButton color="danger" :isDisabled="false">Danger Button</BaseButton>
    <BaseButton color="danger" :isDisabled="true">Disabled Danger Button</BaseButton>
    
    <!-- New Button for Disabling -->
    <BaseButton :isDisabled="isButtonDisabled" @click="handleClick">Click Me (2s Disabled)</BaseButton>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
  name: 'HomePage',
  components: {
    BaseButton
  },
  data() {
    return {
      isButtonDisabled: false
    };
  },
  methods: {
    handleClick() {
      // Disable the button
      this.isButtonDisabled = true;

      // Create a promise that resolves after 2 seconds
      return new Promise((resolve) => {
        setTimeout(() => {
          this.isButtonDisabled = false; // Re-enable the button
          resolve(); // Resolve the promise
        }, 2000);
      });
    }
  }
}
</script>

<style scoped>
/* Add additional styles for HomePage if needed */
</style>