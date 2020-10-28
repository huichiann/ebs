<template>
    <div>
        <v-card class="pa-8" height="530px">
            <v-row>
                <v-col cols="7" class="blue--text" >
                    CLINICS IN SINGAPORE
                </v-col>
                <v-col cols="5" >
                    <v-text-field
                        label="Search"
                        single-line
                        outlined
                        dense
                        rounded
                    ></v-text-field>
                </v-col>
            </v-row>
            <v-row>
                <v-col cols="3" class="blue--text text-lg-center">
                    Clinic Name
                </v-col>
                <v-col cols="3" class="blue--text text-lg-center">
                    Address
                </v-col>
                <v-col cols="3" class="blue--text text-lg-center">
                    # in queue
                </v-col>
                <v-col cols="3" class="blue--text text-lg-center">
                    Wait time
                </v-col>
            </v-row>
            <div class="clinicList">
                <v-card v-for="clinic in clinics" :key="clinic.name" class="mb-3" @click="viewClinic(clinic)">
                    <v-row>
                        <v-col cols="3" class="text-lg-center">{{clinic.name}}</v-col>
                        <v-col cols="3" class="text-lg-center">{{clinic.address}}</v-col>
                        <v-col cols="3" class="text-lg-center">{{clinic.queue}}</v-col>
                        <v-col cols="3" class="text-lg-center">{{clinic.waitTime}}</v-col>
                    </v-row>
                </v-card>
            </div>
        </v-card>
    </div>
</template>

<script>
export default {
    name: 'clinicList',
    props: ["clinics"],
    methods: {
        viewClinic: function(clinic) {
            console.log(clinic)
        },
    }
}
</script>

