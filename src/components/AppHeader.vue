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
        <div class="title">
            <h1>Boolflix</h1>
        </div>
        <div class="search">
            <SearchBar @searchClicked="$emit('searchClicked')" />
        </div>
    </header>

</template>

<style lang="scss" scoped>
header {
    display: flex;
    position: fixed;
    top: 0;
    left: 0;
    padding: 30px;
    height: 150px;
    width: 100%;
    background-color: black;

    .title {
        width: 70%;

        h1 {
            color: red;
        }
    }

    .search {
        width: 30%;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }
}
</style>