<template>
    <v-card
            class="mx-auto"
            width="500"
            height="620"
    >
        <v-container fluid>
            <v-row dense>
                <v-col
                        v-for="card in cards"
                        :key="card.title"
                        :cols="card.flex"
                >
                    <v-card>
                        <v-img
                                :src="card.src"
                                class="white--text align-end"
                                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                        >
                        </v-img>
                    </v-card>
                </v-col>
            </v-row>
        </v-container>
    </v-card>
</template>

<script>
    export default {
        name: "ImageCardComponent",
        data: () => ({
            cards: [
               // { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 12 },
            ],
        }),
    }
</script>

<style scoped>

</style>