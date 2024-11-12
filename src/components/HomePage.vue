<template>
  <div>
    <h2>Welcome to the Home Page!</h2>
    <div v-if="user">
    <h1>Bienvenue, {{ user.name }} !</h1>
  </div>
    <BaseButton color="primary" :isDisabled="false">Primary Button</BaseButton>
    <BaseButton color="warn" :isDisabled="false">Warn Button</BaseButton>
    <BaseButton color="danger" :isDisabled="false">Danger Button</BaseButton>
    <!-- <BaseButton color="danger" :isDisabled="true">Disabled Danger Button</BaseButton>
    
    Button with increasing wait time 
    <BaseButton :isDisabled="isButtonDisabled" @click="handleClick">Click Me (Wait: {{ waitTime }}s)</BaseButton>-->
  
    <AsyncButton :color="'primary'" :delay="clicks" @click="increaseClicks">
      Cliquer pour ralentir ({{ clicks }} secondes d'attente) !
    </AsyncButton>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue';
import AsyncButton from './AsyncButton.vue';
import { signInAndGetUser } from '../lib/microsoftGraph';

export default {
  name: 'HomePage',
  props: {
    user: {
      type: Object,
      default: null
    }
  },
  components: {
    BaseButton,  AsyncButton
  },
  data() {
    return {
      clicks: 1 // Initialise le compteur à 1
    };
  },
  
  methods: {
    increaseClicks() {
      this.clicks += 1; // Incrémente le compteur à chaque clic
    },
    async signInWithMicrosoft() {
      const user = await signInAndGetUser();
      this.$emit('user-signed-in', user);
    }
  }
}
</script>

<style scoped>
/* Add additional styles for HomePage if needed */
</style>