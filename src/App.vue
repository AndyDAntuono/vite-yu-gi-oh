<script>
import { store } from './store.js';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';

export default {
  components: {
    AppHeader
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
  <div class="container">
    <div class="row">
      
    </div>
  </div>

</template>

<style lang="scss" scoped>

</style>
