<script>
import MainCardList from './MainCardList.vue'
import axios from 'axios';

export default {
    components: {
        MainCardList
    },
    data() {
        return {
            cardList: []
        }
    },
    methods: {
        getCardList(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
            .then((response) => {
                // handle success
                console.log(response.data.data);
                this.cardList = response.data.data
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
        }
    },
    created(){
        this.getCardList()
    }
}
</script>

<template>
    <main>
        <MainCardList :cardList="cardList"/>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variable' as *;

</style>