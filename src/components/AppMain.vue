<script>
import { store } from '../store';
import AppCard from './AppCard.vue';

export default{
    name: "AppMain",
    data(){
        return{
            store,
        }
    },
    components:{
        AppCard
    }
}</script>


<template>
    <h2>Le carte:</h2>
    <div id="container">
        <AppCard v-for="card in store.cards" :immagine="card.card_images[0].image_url "
        :nome="card.name" :tipo="card.type">
        </AppCard>
    </div>
</template>


<style scoped lang="scss">
    #container{
        max-width: 950px;
        margin: 0 auto;
        display: flex;
        flex-wrap: wrap;
        gap: 30px;
    }

    h2{
        color: yellow;
        font-size: 2em;
        text-align: center;
        margin-bottom: 30px;
        text-transform: uppercase;
        text-shadow: 3px 2px black;
    }
</style>