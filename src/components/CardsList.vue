<template>
    <div class="container">
        <div class="row">
            <!--<div class="col-4" v-for="card in cards" :key="card.id">
                {{ card.name }}
            </div>-->
            <div class="col-4" v-for="card in store.cardsList" :key="card.id">
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