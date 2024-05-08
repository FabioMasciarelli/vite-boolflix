<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store';
import axios from 'axios';

export default {
    components : {
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
                console.log(resp);
                this.store.moviesArray = null
            })
        }
    }
}
</script>

<template>


    <AppHeader />
    <AppMain @searchClicked="apiMoviesRequest"/>

</template>

<style>

</style>
