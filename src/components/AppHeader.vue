<script>
import { store } from '../store.js';
import SearchBar from './SearchBar.vue';

export default {
    components: {
        SearchBar
    },
    data() {
        return {
            store,
            userSearch: null
        }
    }
}
</script>

<template>

    <SearchBar />

</template>

<style lang="scss" scoped></style>