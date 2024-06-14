<script>
import { store } from '../store';

export default {
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <div class="container my-3">
        <div class="row">
            <div class="col-3">
                <select class="form-select" aria-label="Default select example" v-model="store.searchedArchetype">
                    <option selected>Select an archetype</option>
                    <option v-for="(archetype,index) in store.archetypes" @click="$emit('searched')"> {{store.archetypes[index].archetype_name}}</option>
                </select>
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>