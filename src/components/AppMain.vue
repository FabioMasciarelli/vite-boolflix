<script>
import { store } from '../store.js';
import AppCard from './AppCard.vue/';

export default {
    components: {
        AppCard
    },
    data() {
        return {
            store
        }
    }
}
</script>


<template>

    <div class="main">
        <p v-if="store.moviesArray.length > 0">La tua ricerca ha prodotto {{ store.moviesArray.length + store.seriesArray.length }} risultati</p>
        <AppCard />
    </div>

</template>


<style lang="scss" scoped>

.main {
    margin-top: 150px;
    background-color: black;

    p {
        color:white;
    }
}
</style>