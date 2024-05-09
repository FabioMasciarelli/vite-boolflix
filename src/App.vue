<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store';
import axios from 'axios';

export default {
    components: {
        AppHeader,
        AppMain
    },

    data() {
        return {
            store
        }
    },
    methods: {
        apiMoviesRequest() {
            axios.get(`https://api.themoviedb.org/3/search/movie?api_key=5de2f0b2385fbfdb3a3da0baad756512&query=${store.userQuery}`).then((resp) => {
                this.store.moviesArray = resp.data.results;
                console.log(this.store.moviesArray);
            })
        },
        apiSeriesrequest() {
            axios.get(`https://api.themoviedb.org/3/search/tv?api_key=5de2f0b2385fbfdb3a3da0baad756512&&query=${store.userQuery}`).then((resp) => {
                this.store.seriesArray = resp.data.results;
                console.log(this.store.seriesArray);
            })
        }
    }
}
</script>

<template>


    <AppHeader @searchClicked="apiMoviesRequest(), apiSeriesrequest()" />
    <AppMain />

</template>

<style></style>
