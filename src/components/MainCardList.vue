<script>
import MainSingleCard from './MainSingleCard.vue';

export default {
    data() {
        return {
        }
    },
    components: {
        MainSingleCard
    },
    props: {
        cardList: {
            type: Array,
            required: true
        }
    }
}
</script>

<template>
    <section class="container">
        <div class="row">
            <MainSingleCard v-for="(card,index) in cardList" :key="index" :card="card"/>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variable' as *;

</style>