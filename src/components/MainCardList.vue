<script>
import MainSingleCard from './MainSingleCard.vue'

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
            <div class="col-5th" v-for="(card,index) in cardList" :key="index">
                <div class="card w-100">
                    <img :src="card.card_images[0].image_url" class="card-img-top" :alt="card.name">
                    <div class="card-body">
                        <h2 class="card-title">{{ card.name }}</h2>
                        <p class="card-text">{{ card.archetype }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variable' as *;

.col-5th {
            flex: 0 0 20%;
            max-width: 20%;
        }

</style>