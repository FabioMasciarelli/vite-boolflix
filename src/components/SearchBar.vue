<script>
import { store } from '../store.js';


export default {

    data() {
        return {
            store
        }
    }
}
</script>


<template>

    <div>
        <input type="text" placeholder="Cosa vuoi guardare?" v-model="store.userQuery" aria-label="">
        <button @click="$emit('searchClicked')">Cerca</button>
    </div>

</template>


<style lang="scss" scoped>
    input {
        border: 0;
        padding: 12px 16px;
        border-top-left-radius: 3px;
        border-bottom-left-radius: 3px;
    }

    button {
        border: 0;
        padding: 12px 16px;
        background-color: red;
        border-top-right-radius: 3px;
        border-bottom-right-radius: 3px;
    }
</style>