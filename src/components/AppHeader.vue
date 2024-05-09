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
    <header>

        <SearchBar />
    </header>

</template>

<style lang="scss" scoped>

header {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    padding: 30px;
    height: 150px;
    width: 100%;
    background-color: black;
}

</style>