<template>
  <div class="home">
    <v-row class="mx-12 pt-12">
        <v-col cols="8">
            <ClinicList :clinics="clinics"/>
        </v-col>
        <v-col cols="1"></v-col>
        <v-col cols="3">
            <MakeAppt :items="items"/>
        </v-col>
    </v-row>

    <v-row>
        <v-col>
            <div id="chatbot">
                
            </div>
        </v-col>   
    </v-row>
  </div>
</template>

<script>
import ClinicList from '../components/ClinicList'
import MakeAppt from '../components/MakeAppt'
export default {
    name: 'Home',
    components: {
        ClinicList,
        MakeAppt
    },
    data() {
        return {
            items: [
                    'Pauk 1',
                    'Pail 2'
                ],
            clinics: [
                {name: 'paul clinic', address: 'paul house', queue: '12', waitTime: '2 hours'},
                {name: 'hc clinic', address: 'paul house', queue: '12', waitTime: '2 hours'},
                {name: 'ethel clinic', address: 'paul house', queue: '12', waitTime: '2 hours'},
                {name: 'brem clinic', address: 'paul house', queue: '12', waitTime: '2 hours'},
                {name: 'daryl clinic', address: 'paul house', queue: '12', waitTime: '2 hours'},
                {name: 'daryl2 clinic', address: 'paul house', queue: '12', waitTime: '2 hours'},
            ]
        }
    },
    async mounted() {
        try {
            console.log("try")
            let s = document.createElement("script")
            s.setAttribute('src',"https://cdn.cai.tools.sap/webchat/webchat.js");
            s.setAttribute('channelId',"a6ef0948-b961-4f73-8210-7c364d9b1053");
            s.setAttribute('token',"bf5b60b94bcb34fd41019c9d711b0d79");
            s.setAttribute('id',"cai-webchat");

            let chatbot = document.getElementById("chatbot")
            chatbot.appendChild(s)
        } catch (error) {
            console.log(error)
        }
    },
    methods: {

    }
}
</script>

<style >
.home {
    width: 100%;
    height: 100%;
    background-image: url("../assets/medical_wallpaper.jpg");
    background-position: center;
	background-repeat: no-repeat;
	background-size: cover;
}

.clinicList {
    height: 300px;
    overflow-y: scroll;
    overflow-x: hidden;
}
</style>
