<template>
   <div>
         <h1>Witaj, {{this.$parent.user}}</h1>
  
       <button @click="logout()" >Wyloguj</button>
     
   </div>
</template>

<script>



export default {
    
   props: ['user'],// chce od rodzica uzytkownika
 data() {
     return {
        
         user: '',
       
     }
 },

 methods: {
     logout() {
         this.$emit('logout', false);
     },
    
}

 
}
</script>