<template>
  <LoginComponent v-if="!loggedIn" v-bind=loginData  v-on:login="login($event)"/>
  <MainComponent v-else-if="loggedIn"/>
</template>

<script>


import LoginComponent from "./components/LoginComponent";
import MainComponent from "./components/MainComponent";

export default {
  name: 'App',
  props: {
    source: String,
  },
  components: {
    MainComponent,
    LoginComponent
  },

  data: () => ({
    loggedIn: false,
    loginData: null,
    showPassword: false,
    users: [
      {
        username: 'admin',
        password: 'admin'
      }
    ]
  }),
  methods: {
    login(event){
      for(let user of this.users){
        if(event.username === user.username && event.password === user.password){
          this.loggedIn = true;
        }
      }
    }
  }
};
</script>
