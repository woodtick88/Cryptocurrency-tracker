<template>
    <v-app>
        <v-layout row>
            <v-flex xs12 sm10 offset-sm1>
                <v-card>
                    <v-toolbar color="blue" dark>
                        <v-toolbar-title>Tracker</v-toolbar-title>
                        <v-spacer></v-spacer>
                        <span> USD | EURO </span>
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

import axios from "axios"


export default {
  data () {
    return {
        cryptocurrencies: [],
        errors: [],
        images: {
             BTC: 'https://www.cryptocompare.com/media/19633/btc.png',
             IOT: 'https://www.cryptocompare.com/media/1383540/iota_logo.png',
             ETH: 'https://www.cryptocompare.com/media/20646/eth_logo.png',
             XMR: 'https://www.cryptocompare.com/media/19969/xmr.png',
             LTC: 'https://www.cryptocompare.com/media/19782/litecoin-logo.png',
             ZEC: 'https://www.cryptocompare.com/media/351360/zec.png',
             ZCL: 'https://www.cryptocompare.com/media/351926/zcl.png'
         }
    }
  },
  created() {
      axios.get('https://min-api.cryptocompare.com/data/pricemulti?fsyms=BTC,ETH,ZEC,ZCL,IOT,LTC,XMR&tsyms=USD,EUR')
        .then(response => {
            console.log(response.data)
            this.cryptocurrencies = response.data;
        }).catch(error => this.errors.push(error));
  },
  name: 'App'
}
</script>
