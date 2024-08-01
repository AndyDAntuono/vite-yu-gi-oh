<template>
    <div class="container">
        <div class="row">
            <!--<div class="col-4" v-for="card in cards" :key="card.id">
                {{ card.name }}
            </div>-->
            <div class="col-3 PY-2" v-for="card in store.cardsList" :key="card.id">
                <div class="card mb-3">
                    <img :src="card.card_images[0].image_url" alt="">
                    <div class="card-title">
                        {{ card.name }}
                    </div>
                </div>
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
<style lang="scss" scoped>
    
</style>