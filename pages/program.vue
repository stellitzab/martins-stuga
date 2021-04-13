<template>
    <v-container fluid>
        <h1> Utforska stuglivets erbjudanden </h1>
        <v-row align="center" justify="space-between" class="offer-list">
            <v-col
            v-for="(item) in offer"
            :key="item.title"
            cols="12"
            :sm="4"
            :class="`offer ${item.class}`">

            <v-row align="center" justify="center">
                
                <v-col cols="3" offset="1"> 
                    <v-img :alt="item.alt" :src="item.icon" max-height="200px" max-width="200px" contain/>
                </v-col>

                <v-col cols="8">
                    <p>{{item.text}}</p>
                </v-col>
                
            </v-row>

            </v-col>

        </v-row>

        <v-carousel height="80vh" cycle hide-delimiter-background show-arrows-on-hover>
            <v-carousel-item
                v-for="(item, i) in imagelist"
                :key="i"
                :src="item.image"
            ></v-carousel-item>
        </v-carousel>
    <v-container>
    </v-container>
    </v-container>
</template>


<style scoped>
    h1 {
        padding: 20px;
        color: white;
    }

    p {
        color: white;
    }

    .offer {
        text-align: left;
    }

    .offer-list {
        padding-bottom: 10%;
        padding-top: 6%;
    }
</style>

<script>

import BookButtonVue from '../components/BookButton.vue'

export default {

    components: {
        BookButtonVue,
    },

    data() {
        return {
        offer: [
            {
                text: 'Njut av en ljus sommarnatt vid eldstaden, kanske med ett glas vin men aldrig utan mygg',
                icon: require('~/assets/fireplace.svg'),
                alt: 'fire-place',
                class: 'fire-place',
            },
            {
                text: 'Med bara någon kilometer till polcirkeln bjuds här på fototillfällen med (nästan) äkta midnattssol',
                icon: require('~/assets/camera.svg'),
                alt: 'food',
                class: 'cook-food',
            },
            {
                text: 'Klassiker som kokkaffe över elden ingår självklart i grundpaketet',
                icon: require('~/assets/kaffekokare.svg'),
                alt: 'sun',
                class: 'sun-relax',
            },
        ],
            imagelist: [
                {
                    image: require('~/assets/photos/1.jpg'),
                    text: 'look at how fun this is',
                },
                {
                    image: require('~/assets/photos/2.jpg'),
                    text: 'look at how fun this is',
                },
                {
                    image: require('~/assets/photos/3.jpg'),
                    text: 'look at how fun this is',
                },
                {
                    image: require('~/assets/photos/4.jpg'),
                    text: 'look at how fun this is',
                },
            ],
        }
    },
    
}
</script>