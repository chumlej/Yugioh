<template>
    <v-layout row justify-center>
        <v-dialog v-model="isDialogOpen" max-width="600px">
            <v-card>
                <v-card-title>
                    <span class="headline">Karte / Display hinzufügen</span>
                </v-card-title>
                <v-card-text>
                    <v-container grid-list-md>
                        <v-layout wrap>
                            <v-flex xs12 sm6>
                                <v-text-field label="Displayname" ></v-text-field>
                            </v-flex>
                            <v-flex xs12 sm6>
                                <v-text-field
                                        label="Kartenname"
                                ></v-text-field>
                            </v-flex>
                            <v-flex xs12>
                                <v-text-field label="Cardmarket-URL*"  ></v-text-field>
                            </v-flex>
                            <v-flex xs12 sm6>
                                <v-select
                                        :items="['0-17', '18-29', '30-54', '54+']"
                                        label="Display*"
                                ></v-select>
                            </v-flex>
                            <v-flex xs12 sm6>
                                <v-autocomplete
                                        :items="['Skiing', 'Ice hockey', 'Soccer', 'Basketball', 'Hockey', 'Reading', 'Writing', 'Coding', 'Basejump']"
                                        label="Karte"
                                ></v-autocomplete>
                            </v-flex>
                            <v-flex xs12>
                                <v-file-input label="Bild hinzufügen"></v-file-input>
                            </v-flex>
                        </v-layout>
                    </v-container>
                    <small>*Nur eine Variante zum Hinzufügen benutzen</small>
                </v-card-text>
                <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn color="blue darken-1" flat @click="dialogClosed(false)">Close</v-btn>
                    <v-btn color="blue darken-1" flat @click="dialogClosed(false)">Save</v-btn>
                </v-card-actions>
            </v-card>
        </v-dialog>
    </v-layout>
</template>

<script>
    export default {
        name: "AddCardComponent",
        props: {
            source: String,
            isDialogOpen: Boolean
        },
        methods: {
            dialogClosed(event){
                this.$emit('dialogClosed', event)
            }
        }
    }
</script>

<style scoped>

</style>