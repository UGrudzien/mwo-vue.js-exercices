<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1> Witaj w systemie zapisów na zajęcia</h1>

      
        <div v-if="!isAutenticated">Zalogu sie emailem: 
        <input type="email" v-model="email">
        <button class="button button-clear" @click="toggle()">Zaloguj</button>
        </div>

    <div v-else>
      <h1>Witaj, {{email}}</h1>
      <button  @click ="toggle()"> Wyloguj</button>
    </div>

  </div>
</template>

<script>
import "milligram";
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
