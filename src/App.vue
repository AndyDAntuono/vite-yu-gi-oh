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
      axios.get(store.apiUrl).then((result) => {
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
