<template>
    <button 
      :class="['base-button', colorClass, { 'disabled': isDisabled }]"
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
      },
      color: {
        type: String,
        default: 'primary',
        validator: value => {
          return ['primary', 'warn', 'danger'].includes(value);
        }
      }
    },
    computed: {
      colorClass() {
        return `button-${this.color}`;
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
    color: white;
    border: none;
    border-radius: 4px;
    padding: 10px 20px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.2s;
  }
  
  .button-primary {
    background-color: #42b983;
  }
  
  .button-primary:hover {
    background-color: #36a76e;
  }
  
  .button-warn {
    background-color: #f0ad4e;
  }
  
  .button-warn:hover {
    background-color: #ec971f;
  }
  
  .button-danger {
    background-color: #d9534f;
  }
  
  .button-danger:hover {
    background-color: #c9302c;
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