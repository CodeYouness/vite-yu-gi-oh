<script>
import MainCardList from './MainCardList.vue'
import axios from 'axios';
import { store } from '../store';
import MainLoader from './MainLoader.vue'
import AppSearch from './AppSearch.vue'

export default {
    components: {
        MainCardList,
        MainLoader,
        AppSearch
    },
    data() {
        return {
            store,
            isLoaded: false
        }
    },
    methods: {
        getCardList(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
            .then((response) => {
                // handle success
                console.log(response.data.data);
                this.store.cardList = response.data.data
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
        },
        getArchetypeList(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then((response) => {
                // handle success
                console.log(response.data);
                this.store.archetypes = response.data
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
        },
        loadingTime(){
            setTimeout( () => {
                this.isLoaded = true
            }, 3000)
        },
        consoletry(){
            console.log('okay')
        }
        
    },
    created(){
        this.getCardList()
        this.getArchetypeList()
        this.loadingTime()
    }
}
</script>

<template>
    <main class="bg-secondary overflow-y-scroll">
        <AppSearch v-if="isLoaded" @searched="consoletry"/>
        <MainCardList v-if="isLoaded"/>
        <MainLoader v-else/>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variable' as *;

main {
    height: calc(100vh - 67.35px);
}

</style>