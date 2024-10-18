<template>
    <button 
      :class="['base-button', { 'disabled': isDisabled }]"
      :disabled="isDisabled"
      @mouseover="hover = true"
      @mouseleave="hover = false"
      @focus="focus = true"
      @blur="focus = false"
    >
      <slot></slot>
    </button>
  </template>
  
  <script>
  export default {
    name: 'BaseButton',
    props: {
      isDisabled: {
        type: Boolean,
        default: false
      }
    },
    data() {
      return {
        hover: false,
        focus: false
      };
    }
  };
  </script>
  
  <style scoped>
  .base-button {
    background-color: #42b983;
    color: white;
    border: none;
    border-radius: 4px;
    padding: 10px 20px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.2s;
  }
  
  .base-button:hover {
    background-color: #36a76e;
  }
  
  .base-button:focus {
    outline: none;
    box-shadow: 0 0 5px rgba(66, 184, 131, 0.5);
  }
  
  .base-button.disabled {
    background-color: #cccccc;
    cursor: not-allowed;
  }
  
  .base-button.disabled:hover {
    background-color: #cccccc;
  }
  </style>