<template>
    <div class="container">
        <div class="row">
            <!--<div class="col-4" v-for="card in cards" :key="card.id">
                {{ card.name }}
            </div>-->
            <!--COSA CAVOLO DEVO SCRIVERE PER SELEZIONARE L'IMMAGINE?!?!-->
            <div class="col-4" v-for="card in store.cardsList" :key="card.id">
                <img :src="card.card_images[0].image_url" alt="">
                {{ card.name }}
            </div>
        </div>
    </div>
</template>
<script>
import { store } from '../store';

//import { store } from '../store';

export default {
    //props: {
    //    cards: Array
    //},

    data() {
        return {
            store
        }
    }
}
</script>
<style lang="scss">
    
</style>