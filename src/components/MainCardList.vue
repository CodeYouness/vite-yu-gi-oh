<script>
import MainSingleCard from './MainSingleCard.vue';
import { store } from '../store';

export default {
    data() {
        return {
            store
        }
    },
    components: {
        MainSingleCard,
        store
    },
}
</script>

<template>
    <section class="container bg-white overflow-y-scroll">
        <div class="row">
            <MainSingleCard v-for="(card,index) in store.cardList" :key="index" :card="card"/>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variable' as *;

</style>