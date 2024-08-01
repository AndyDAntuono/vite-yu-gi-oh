<script>
import { store } from './store.js';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';

export default {
  components: {
    AppHeader,
    CardsList,
  },
  created() {
    this.getCardsList(),
    this.selectArchetype()
  },
  methods: {
    getCardsList(){
      if (store.cardArchetype != '') {
        store.apiUrl += `&archetype=${store.cardArchetype}`
      }
      // Effettua una richiesta GET all'URL specificato da store.apiUrl utilizzando Axios
      axios.get(store.apiUrl).then((result) => {
        //Se la richiesta ha successo, assegna i dati ottenuti (result.data.data) a store.cardsList
        //this.cardsList = result.data.data;
        store.cardsList = result.data.data;
      });
    },
    selectArchetype(){
      axios.get(store.apiArcheUrl).then((result) => {
        store.archetypeList = result.data;
      })
    }
  },
  data() {
    return {
      store,
      //cardsList: []
    }
  }
}

</script>

<template>
  <AppHeader />
  <main>
    <!-- <CardsList :cards="cardsList"/> -->
    <CardsList @filter="getCardsList"/>
  </main>
</template>

<style lang="scss">
@use './styles/generals.scss';
</style>
