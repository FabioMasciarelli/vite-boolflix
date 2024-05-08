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
        <input type="text" placeholder="Cosa vuoi guardare?" v-model="store.userQuery">
        <button @click="$emit('searchClicked')">Cerca</button>
    </div>

</template>


<style lang="scss" scoped></style>