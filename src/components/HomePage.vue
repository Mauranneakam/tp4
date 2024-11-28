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
  
    <AsyncButton color="primary" :disabled="isLoggedIn" @click="signInWithMicrosoft">Sign In with Microsoft</AsyncButton>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue';
import AsyncButton from './AsyncButton.vue';
import { signInAndGetUser } from '../lib/microsoftGraph';
import { mapGetters, mapMutations } from 'vuex';

export default {
  name: 'HomePage',
  computed: {
    ...mapGetters(['getUser']),
    user() {
      return this.getUser
    },
    isLoggedIn() {
      return !!this.user;
    }
  },
  components: {
    BaseButton,  AsyncButton
  },
  data() {
    return {
      clicks: 1 
    };
  },
  
  methods: {
    ...mapMutations(['setUser']),
    increaseClicks() {
      this.clicks += 1; // Incrémente le compteur à chaque clic
    },
    async signInWithMicrosoft() {
      const user = await signInAndGetUser();
      this.setUser(user);
    }
  }
}
</script>

<style scoped>
/* Add additional styles for HomePage if needed */
</style>