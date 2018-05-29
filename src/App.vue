<template>
  <div id="app">
    <img src="./assets/logo.png" />
    <h1> Witaj w systemie zapisów na zajęcia</h1>
       
     <div v-if="!isAutenticated">


          <login-form @login="logMeIn($event)" ></login-form>

          <login-form @login="logMeIn($event)" :button-label="'Wejdź'"></login-form>
          <!-- <login-form @login="logMeIn($event)" :button-label="'Wleć'"></login-form>
          <login-form @login="logMeIn($event)" :button-label="'Zaloguj się jak człowiek'"></login-form> -->
        </div>



        <div v-else>
          <h1>Witaj, {{email}}</h1>
          <button  @click ="toggle()"> Wyloguj</button>
       </div>

  </div>
</template>

<script>
import "milligram";

import LoginForm from "./LoginForm";
export default {
   components: {LoginForm},
  name: 'app',
  data () {
    
    return {
      
       email: "",
        isAutenticated: false,
    
    };
  },
  methods: {
  alertMyEmail() {
    alert(this.email);
  },

  toggle(){
    this.isAutenticated= !this.isAutenticated
  },
  logMeIn(username) {
    this.isAutenticated = !this.isAutenticated;
    this.authenticatedUsername = username;
}
}

}

</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
  background-color: beige;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
