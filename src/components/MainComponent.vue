<template>
    <v-app id="inspire">
        <v-navigation-drawer
                v-model="drawer"
                app
                clipped
        >
            <v-list dense>
                <v-list-item link>
                    <v-list-item-action>
                        <v-icon>mdi-view-dashboard</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title>Dashboard</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-list-item link>
                    <v-list-item-action>
                        <v-icon>mdi-settings</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title>Settings</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>

        <v-app-bar
                app
                clipped-left
        >
            <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
            <v-toolbar-title>Yugioh Prize Tracker</v-toolbar-title>
        </v-app-bar>

        <v-content>
            <v-container
                    class="fill-height"
                    fluid
            >
                <AddCardComponent :isDialogOpen="addCardDialogOpen" v-on:dialogClosed="addCardDialogOpen = false"></AddCardComponent>
                <ImageGalleryComponent :cards="cards"></ImageGalleryComponent>
                <v-btn class="mx-2" fab dark color="indigo" absolute="true" right="true" style="bottom: 2em"
                 @click="addCardDialogOpen = true">
                    <v-icon dark>mdi-plus</v-icon>
                </v-btn>
            </v-container>
        </v-content>

        <v-footer app>
            <span>&copy; PKLL Productions</span>
        </v-footer>
    </v-app>
</template>

<script>

import AddCardComponent from "./AddCardComponent";
import ImageGalleryComponent from "./ImageGalleryComponent";


export default {
    props: {
        source: String,
    },
    components: {
        ImageGalleryComponent,
        AddCardComponent
    },
    data: () => ({
        drawer: null,
        addCardDialogOpen: false,
        cards: [
            {
                name: 'Auszubildende Illusionsmagierin ',
                image: require('../assets/Auszubildende Illusionsmagierin.jpg'),
                price: '1,00',
                preistrend: require('../assets/Auszubildende Illusionsmagierin Pricegraph.jpg')
            },
            {
                name: 'Seelen der Magier',
                image: require('../assets/Seelen der Magier.jpg'),
                price: '73,50',
                preistrend: require('../assets/Seelen der Magier Trend.jpg')
            },
            {
                name: 'Elementar-HELD Sunrise',
                image: require('../assets/Elementar-HELD Sunrise.jpg'),
                price: '5,90',
                preistrend: require('../assets/Elementar-HELD Sunrise Trend.jpg')
            },
            {
                name: 'Ignition Assault Display ',
                image: require('../assets/Ignition Assault Display.jpg'),
                price: '49,64',
                preistrend: require('../assets/Ignition Assault Trend.jpg')
            },
            {
                name: 'Seelendiener',
                image: require('../assets/Seelendiener.jpg'),
                price: '5,00',
                preistrend:require('../assets/Seelendiener Trend.jpg')
            }
        ]
    }),
    created () {
        this.$vuetify.theme.dark = true
    },
}
</script>