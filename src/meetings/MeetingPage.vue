<template>
    <div>
       <h2>Zajęcia</h2>
       <new-meeting-form @added="addNewMeeting($event) "></new-meeting-form>
       <meetings-list :meetings="meetings" :participant="user"></meetings-list>
    </div>
</template>

<script>
import NewMeetingForm from "./NewMeetingForm";
import MeetingsList from "./MeetingsList";

export default {
     props: ["user"],
  components: {NewMeetingForm, MeetingsList},
 
  data() {
      return {
          meetings: [],
          participant:"",
      };
  },
  methods: {
      addNewMeeting(meeting) {
          this.meetings.push(meeting);
      },
    //   addParticipant(){
    //       return
    //       this.participant = user
          
    //   }
  }
}
</script>