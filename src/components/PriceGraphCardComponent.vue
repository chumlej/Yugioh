<template>
    <v-card
            class="mx-auto"
            width="52.5%"
            height="47%"
    >
                        <v-img
                                :src="pricetrend"
                                class="white--text align-end"
                                contain
                                max-height="375px"
                                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                        >
                        </v-img>
    </v-card>
</template>

<script>
    export default {
        name: "PriceGraphCardComponent",
        props: {
          pricetrend: String
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