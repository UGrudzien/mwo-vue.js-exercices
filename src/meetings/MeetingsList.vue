<template>
    <table v-if="meetings.length > 0">
        <thead>
            <tr>
                <th>Nazwa spotkania</th>
                <th>Opis</th>
                 <th>Użytkownicy</th>
                  <th> </th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="meeting in meetings" :key="meeting.name">
                <td>{{ meeting.name }}</td>
                <td>{{ meeting.description }}</td>
                <td >{{participant}}</td>
                <td><button @click= save()>Zapisz się</button> </td>
            </tr>
        </tbody>
    </table>
</template>

<script>
    // props: ['meetings', 'user']
export default {
 props: ['meetings', 'participant'],

 data() {
      return {
          meetings: [],
          participant:"",
      };
  },
}
// methods:{
//     save(){
     
//     }
// }

</script>