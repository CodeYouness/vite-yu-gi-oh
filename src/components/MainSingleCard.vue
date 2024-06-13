<script>
export default {
    data() {
        return {
        }
    },
    props: {
        card: {
            type: Object,
            required: true
        }
    }
}
</script>

<template>
    <div class="col-5th my-3">
        <section class="card bg-secondary">
            <img :src="card.card_images[0].image_url" class="card-img-top" :alt="card.name">
            <div class="card-body">
                <h2 class="card-title fs-5">{{ card.name }}</h2>
                <p class="card-text">{{ card.archetype }}</p>
            </div>
        </section>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variable' as *;

.col-5th {
            flex: 0 0 20%;
            max-width: 20%;
        }

</style>