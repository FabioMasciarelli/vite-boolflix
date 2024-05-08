<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            store,
            source: ''
        }
    },
    methods: {
        flagImage(cardInfo) {
            switch (cardInfo.original_language) {
                case 'it':
                    return '../assets/italy.svg.png';
                case 'fr':
                    return '../assets/france.svg.png';
                case 'en':
                    return '../assets/uk.png';
                case 'ja':
                    return '../assets/japan.svg.png';
                default:
                    return cardInfo.original_language
            }
        }
    }
}
</script>


<template>

    <div class="card" v-for="cardInfo in store.moviesArray">
        <div class="card-back">
            <h3>{{ cardInfo.title }}</h3>
            <h4>{{ cardInfo.original_title }}</h4>
            <img :src="flagImage(cardInfo)" alt="">
            <h4>{{ cardInfo.vote_average / 2 }}</h4>
        </div>
        <div class="card-front">

        </div>

    </div>

</template>


<style lang="scss" scoped></style>