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
            return new URL(`${imgName}`, import.meta.url).href;
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
        },
        starIcon(num) {
            console.log(Math.round(num / 2));
            return Math.round(num / 2);
        }
    }
}
</script>


<template>


    <div class="results-list">
        <!-- MOVIES -->
        <section class="movies">
            <div class="card" v-for="movieInfo in store.moviesArray">
                <div class="card-back">
                    <h3>{{ movieInfo.title }}</h3>
                    <h6>{{ movieInfo.original_title }}</h6>
                    <img :src="flagImage(movieInfo.original_language)" :alt="movieInfo.title">
                    <div class="vote">
                        <i class="fas fa fa-solid fa-star" v-for="star in starIcon(movieInfo.vote_average)"></i>
                        <i class="fa-regular fa-star" v-for="star in 5 - starIcon(movieInfo.vote_average)"></i>
                    </div>
                </div>
                <div class="card-front">
                    <img :src="`https://image.tmdb.org/t/p/w342/${movieInfo.poster_path}`" :alt="movieInfo.title">
                </div>

            </div>
        </section>

        <!-- TV SERIES -->
        <section class="series">
            <div class="card" v-for="seriesInfo in store.seriesArray">
                <div class="card-back">
                    <h3>{{ seriesInfo.name }}</h3>
                    <h6>{{ seriesInfo.original_name }}</h6>
                    <img :src="flagImage(seriesInfo.original_language)" :alt="seriesInfo.name" class="flag">
                    <div>
                        <i class="fas fa fa-solid fa-star" v-for="star in starIcon(seriesInfo.vote_average)"></i>
                        <i class="fa-regular fa-star" v-for="star in 5 - starIcon(seriesInfo.vote_average)"></i>
                    </div>
                </div>
                <div class="card-front">
                    <img :src="`https://image.tmdb.org/t/p/w342/${seriesInfo.poster_path}`" :alt="seriesInfo.name"
                        class="path">
                </div>
            </div>
        </section>
    </div>

</template>


<style lang="scss" scoped>
.results-list {

    padding: 20px;

    .movies, .series {
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
    }

    .card {
        border: 20px;
        color: white;
        height: 450px;
        width: calc(100% / 5 - 20px);

        &:hover {
            .card-back {
                display: block;
            }

            .card-front {
                display: none;
            }
        }

        .card-back {
            display: none;
            padding: 20px;

            .flag {
                width: 10px;
            }

            .card-front {
                height: 300px;
                margin: 20px;

            }
        }
    }

}
</style>