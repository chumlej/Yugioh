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
                <ImageCardComponent style="position: absolute; left: 5em" :image="card.image"></ImageCardComponent>
                <PriceGraphCardComponent style="position: absolute; right: 5em; direction: rtl" :pricetrend="card.preistrend"></PriceGraphCardComponent>
                <CardDetailsCardComponent style="position: absolute; right: 5em; top: 36em" :price="card.price"></CardDetailsCardComponent>
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
    props: {
        cards: Object
    },
    data() {
        return {
            color: '#cccccc',
        }
    }
}
</script>

<style scoped>

</style>