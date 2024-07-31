<script>
import { store } from './store.js';
import axios from 'axios';

export default {
  components: {

  },
  created() {
    this.getCardsList()
  },
  methods: {
    getCardsList(){
      axios.get(store.apiUrl).then((result) => {
        store.cardsList = result.data.results
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

</template>

<style lang="scss" scoped>

</style>
