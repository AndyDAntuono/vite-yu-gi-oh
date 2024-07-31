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
    this.getCardsList()
  },
  methods: {
    getCardsList(){
      // Effettua una richiesta GET all'URL specificato da store.apiUrl utilizzando Axios
      axios.get(store.apiUrl).then((result) => {
        //Se la richiesta ha successo, assegna i dati ottenuti (result.data.data) a store.cardsList
        store.cardsList = result.data.data;
      });
    }
  },
  data() {
    return {
      store,

    }
  }
}

</script>

<template>
  <AppHeader />
  <CardsList />

</template>

<style lang="scss" scoped>

</style>
