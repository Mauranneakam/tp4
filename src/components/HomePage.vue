<template>
  <div>
    <h2>Welcome to the Home Page!</h2>
    <BaseButton color="primary" :isDisabled="false">Primary Button</BaseButton>
    <BaseButton color="warn" :isDisabled="false">Warn Button</BaseButton>
    <BaseButton color="danger" :isDisabled="false">Danger Button</BaseButton>
    <BaseButton color="danger" :isDisabled="true">Disabled Danger Button</BaseButton>
    
    <!-- Button with increasing wait time -->
    <BaseButton :isDisabled="isButtonDisabled" @click="handleClick">Click Me (Wait: {{ waitTime }}s)</BaseButton>
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
      isButtonDisabled: false,
      clickCount: 0 // Counter for the number of clicks
    };
  },
  computed: {
    waitTime() {
      // Calculate wait time based on the number of clicks
      return this.clickCount + 1; // Start from 1 second
    }
  },
  methods: {
    handleClick() {
      // Disable the button
      this.isButtonDisabled = true;

      // Increment click count
      this.clickCount++;

      // Create a promise that resolves after the wait time
      return new Promise((resolve) => {
        setTimeout(() => {
          this.isButtonDisabled = false; // Re-enable the button
          resolve(); // Resolve the promise
        }, this.waitTime * 1000); // Convert to milliseconds
      });
    }
  }
}
</script>

<style scoped>
/* Add additional styles for HomePage if needed */
</style>