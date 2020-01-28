<template>
    <v-card
            class="mx-auto"
            width="500"
            height="620"
    >
                        <v-img
                                :src="image"
                                class="white--text align-end"
                                contain
                                max-height="620"
                                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                        >
                        </v-img>
    </v-card>
</template>

<script>
    export default {
        name: "ImageCardComponent",
        props: {
          image: String,
        },
        data: () => ({
            cards: [
               // { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 12 },
            ],

        }),
    }
</script>

<style scoped>

</style>