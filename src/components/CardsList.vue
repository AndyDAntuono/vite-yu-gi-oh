<template>
    <div class="container">
        <div class="row">
            <!--Per ora ottengo solo il nome delle carte poiché non ho ancora modellato alcun contenitore per ospitare gli alti dati delle carte di Yu-Gi-Oh-->
            <div class="col-4" v-for="card in store.cardsList" :key="card.id">
                {{ card.name }}
            </div>
        </div>
    </div>
</template>
<script>
import { store } from '../store';

export default {
    data() {
        return {
            store
        }
    }
}
</script>
<style lang="scss">
    
</style>