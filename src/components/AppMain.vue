<script>
import { store } from '../store.js';
import PropsCard from './PropsCard.vue';

export default {
    components: {
        PropsCard
    },
    data() {
        return {
            store
        }
    }
}
</script>


<template>

    <div>
        <p v-if="store.moviesArray.length > 0">La tua ricerca ha prodotto {{ store.moviesArray.length }} risultati</p>
        <PropsCard />
    </div>

</template>


<style lang="scss" scoped></style>