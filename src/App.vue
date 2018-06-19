<template>
    <v-app>
        <v-layout row>
            <v-flex xs12 sm10 offset-sm1>
                <v-card>
                    <v-toolbar color="blue" dark>
                        <v-toolbar-title>Tracker</v-toolbar-title>
                        <v-spacer></v-spacer>
                        <v-text> USD | EURO </v-text>
                    </v-toolbar>
                    <v-list>
                        <v-list-tile avatar @click="">
                            <v-list-tile-avatar>
                                <img src="'currency_img'">
                            </v-list-tile-avatar>
                            <v-list-tile-content>
                                <v-list-tile-title v-text="'Currency Name'">
                                </v-list-tile-title>
                            </v-list-tile-content>
                            <v-list-tile-action>
                                <span>Currency Price</span>
                            </v-list-tile-action>
                        </v-list-tile>
                    </v-list>
                </v-card>
            </v-flex>
        </v-layout>
    </v-app>
</template>

<script>
export default {
  data () {
    return {

    }
  },
  name: 'App'
}
</script>
