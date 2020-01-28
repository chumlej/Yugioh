<template>
    <v-carousel
            height="99.92%"
            hide-delimiter-background
            show-arrows-on-hover
    >
        <v-carousel-item
                v-for="(card, i) of cards"
                :key="i"
        >
            <v-sheet
                    :color="color"
                    height="100%"
            >
                <v-row
                        class="fill-height"
                        align="top"
                        justify="center"
                        style="padding-top: 5em; height: 19%"
                >
                    <div class="display-3" style="height: 10%">{{ card.name }}</div>
                </v-row>
                <ImageCardComponent style="position: absolute; left: 5em"></ImageCardComponent>
                <PriceGraphCardComponent style="position: absolute; right: 5em; direction: rtl"></PriceGraphCardComponent>
                <CardDetailsCardComponent style="position: absolute; right: 5em; top: 36em"></CardDetailsCardComponent>
            </v-sheet>
        </v-carousel-item>
    </v-carousel>
</template>

<script>

import ImageCardComponent from "./ImageCardComponent";
import PriceGraphCardComponent from "./PriceGraphCardComponent";
import CardDetailsCardComponent from "./CardDetailsCardComponent";

export default {
    name: "ImageGalleryComponent",
    components: {CardDetailsCardComponent, PriceGraphCardComponent, ImageCardComponent},
    data() {
        return {
            color: '#cccccc',
            cards: [
                {
                    name: 'Auszubildende Illusionsmagierin ',
                    image: '../assets/No_image.png',
                    preis: '1,00',
                    preistrend: ''
                },
                {
                    name: 'Seelen der Magier',
                    image: '../assets/No_image.png',
                    preis: '73,50',
                    preistrend: ''
                },
                {
                    name: 'Elementar-HELD Sunrise',
                    image: '../assets/No_image.png',
                    preis: '5,90',
                    preistrend: ''
                },
                {
                    name: 'Ignition Assault Display ',
                    image: '../assets/No_image.png',
                    preis: '49,64',
                    preistrend: ''
                },
                {
                    name: 'Seelendiener',
                    image: '../assets/No_image.png',
                    preis: '5,00',
                    preistrend: ''
                }
            ]
        }
    }
}
</script>

<style scoped>

</style>