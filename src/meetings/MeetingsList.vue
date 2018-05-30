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
                <td>
                   
                   <participant-list :participantList="participants"></participant-list> </td>
                <td>
                    <span v-if="!isSingup">
                        <button @click= save()>zapisz</button>
                        </span>
                    <span v-else>
                        <button @click=resave()></button>
                    </span>
                
                
                
                 </td>
            </tr>
        </tbody>
    </table>
</template>

<script>
    // props: ['meetings', 'user']
    import ParticipantList from "./ParticipantList";
export default {
 props: ['meetings', 'user'],
  components:{ParticipantList},

 data() {
      return {
          meetings: [],
          participant:"user",
          participants:[
            //   {id:"0", text:"Ula"}, 
            //   {id:"1",text:"Ala"}
          ],
          isSingup: false,
      };
  },

methods:{
    participants(){
      this.participant=user
    },
    save(){
        if(this.participant){
            this.participants.push(this.participant);
        }
    },
    resave(){
        
    }
}
}
</script>