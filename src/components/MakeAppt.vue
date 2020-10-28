<template>
    <div>
        <v-card class="pa-8" height="530px" width="100%">
            <div class="apptheader blue--text text-lg-center">
                MAKE APPOINTMENT
            </div>
            <!-- <v-row>
                <v-col cols="1"></v-col>
                <v-col cols="4">
                    <v-btn height="150%" @click="gender='male'">
                        <v-avatar>
                            <img src="../assets/man.png"/>
                        </v-avatar>
                    </v-btn>
                </v-col>
                <v-col cols="2"></v-col>
                <v-col cols="4">
                    <v-btn height="150%" @click="gender='female'">
                        <v-avatar>
                            <img src="../assets/women.png"/>
                        </v-avatar>
                    </v-btn>
                </v-col>
                <v-col cols="1"></v-col>
            </v-row> -->
            <v-select
                v-model="selectedGender"
                :items="gender"
                label="Select your gender"
            ></v-select>
            <v-text-field
                v-model="fullName"
                label="Full Name"
            ></v-text-field>
            <v-text-field
                v-model="phoneNumber"
                label="Phone Number"
            ></v-text-field>
            <v-text-field
                v-model="condition"
                label="Condition"
            ></v-text-field>
            <v-select
                v-model="selectedClinic"
                :items="items"
                label="Select your clinic"
            ></v-select>
            <v-menu
                v-model="menu"
                :close-on-content-click="false"
                transition="scale-transition"
                offset-y
                min-width="290px"
            >
                <template v-slot:activator="{ on, attrs }">
                <v-text-field
                    v-model="date"
                    label="Date"
                    prepend-icon="mdi-calendar"
                    readonly
                    v-bind="attrs"
                    v-on="on"
                ></v-text-field>
                </template>
                <v-date-picker
                v-model="date"
                no-title
                scrollable
                @input="menu=false"
                ></v-date-picker>
            </v-menu>
            <div style="width:200px;" class="mx-auto">
                <v-btn rounded color="primary" @click="processAppt()">
                    BOOK NOW 
                </v-btn>
            </div>
        </v-card>
    </div>
</template>

<script>
export default {
    name: 'makeAppt',
    props: ["items"],
    data() {
        return {
            menu: false,
            date: '',
            fullName: '',
            phoneNumber: '',
            condition: '',
            selectedClinic: '',
            selectedGender: '',
            gender: ['Male', 'Female'],
        }
    },
    methods: {
        processAppt: function() {
            console.log(this.fullName, this.phoneNumber, this.condition, this.selectedClinic, this.date, this.selectedGender)
        }
    }
}
</script>

