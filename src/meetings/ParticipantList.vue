<template>
    <ul>
     <li v-for="person in participantList" :key="person.id">{{person.text}}</li>   
      </ul>
</template>

<script>
export default {
    props:['participantList'],

  data() {
      return {
     
      };
  },
  methods: {
     
    }
  }

</script>
