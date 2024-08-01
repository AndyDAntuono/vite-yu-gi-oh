<!-- Tutto il codice sottostante è puramente concettuale poiché sto cercando di capire come formulare il filtro delle carte -->
<template>
    <div>
      <label>
        Categoria:
        <select v-model="selectedCategory" @change="filterCards">
          <option value="">Tutte</option>
          <option value="categoria1">Categoria 1</option>
          <option value="categoria2">Categoria 2</option>
        </select>
      </label>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        selectedCategory: '',
      };
    },
    methods: {
      filterCards() {
        this.$emit('filter-category', this.selectedCategory);
      },
    },
  };
  </script>
  