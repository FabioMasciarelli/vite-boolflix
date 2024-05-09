<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            store,
            flag: null
        }
    },
    methods: {
        getImageUrl(imgName) {
            return new URL(`${ imgName }`, import.meta.url).href;
        },
        flagImage(lang) {
            switch (lang) {
                case 'it':
                    this.flag = '../assets/img/italy.png';
                    return this.getImageUrl(this.flag);
                    
                case 'fr':
                    this.flag = '../assets/img/france.png';
                    return this.getImageUrl(this.flag)
                case 'en':
                    this.flag = '../assets/img/uk.png';
                    return this.getImageUrl(this.flag)
                case 'ja':
                    this.flag = '../assets/img/japan.png';
                    return this.getImageUrl(this.flag)
                default:
                    return lang;
            }

        }
    }
}
</script>


<template>

    <div class="card" v-for="cardInfo in store.moviesArray">
        <div class="card-back">
            <h3>{{ cardInfo.title }}</h3>
            <h6>{{ cardInfo.original_title }}</h6>
            <img :src="flagImage(cardInfo.original_language)" :alt="cardInfo.title">
            <h4>{{ cardInfo.vote_average / 2 }}</h4>
        </div>
        <div class="card-front">

        </div>

    </div>

</template>


<style lang="scss" scoped></style>