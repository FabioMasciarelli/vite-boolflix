<script>
import {store} from '../store.js';
import PropsCard from './PropsCard.vue';

export default {
    props: {
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
    <PropsCard/>
</div>

</template>


<style lang="scss" scoped>

</style>