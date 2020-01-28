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
                <ImageGalleryComponent></ImageGalleryComponent>
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
    }),
    created () {
        this.$vuetify.theme.dark = true
    },
}
</script>