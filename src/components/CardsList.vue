<template>
    <div class="container">
        <div class="row">
            <div class="col-12">
                <select class="form-select form-select-lg mb-3" v-model="store.cardArchetype" @change="changeCard()">
                    <option selected>Seleziona la carta</option>
                    <option v-for="(cardArchetype, index) in store.archetypeList" :key="index" :value="cardArchetype.archetype_name">
                        {{ cardArchetype.archetype_name }}</option>
                  </select>
            </div>
        </div>
        <div class="row">
            <!--<div class="col-4" v-for="card in cards" :key="card.id">
                {{ card.name }}
            </div>-->
            <div class="col-3 PY-2" v-for="card in store.cardsList" :key="card.id">
                <div class="card mb-3">
                    <img :src="card.card_images[0].image_url" alt="">
                    <div class="card-title">
                        <h5>{{ card.name }}</h5>
                        <p>{{card.archetype}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<!--

Tutto il codice sottostante è puramente concettuale poiché sto cercando di capire come formulare il filtro delle carte

<template>
    <div>
      <CardFilter @filter-category="updateCategory" />
      <div v-if="filteredCards.length > 0">
        <h3>Carte Selezionate</h3>
        <ul>
          <li v-for="card in filteredCards" :key="card.id">
            {{ card.name }} - {{ card.category }}
          </li>
        </ul>
      </div>
      <div v-else>
        <p>Nessuna carta disponibile.</p>
      </div>
    </div>
  </template>
  
  <script>
  import CardFilter from './CardFilter.vue';
  
  export default {
    components: { CardFilter },
    data() {
      return {
        cards: [], // Array per le carte ottenute dall'API
        selectedCategory: '',
      };
    },
    computed: {
      filteredCards() {
        return this.cards.filter(card => 
          (this.selectedCategory === '' || card.category === this.selectedCategory)
        ).slice(0, 20); // Limita a 20 carte
      },
    },
    methods: {
      async fetchCards() {
        // Simula una chiamata all'API
        this.cards = [
          { id: 1, name: 'Carta A', category: 'categoria1' },
          { id: 2, name: 'Carta B', category: 'categoria2' },
          // Aggiungi più carte come necessario
        ];
      },
      updateCategory(category) {
        this.selectedCategory = category;
      },
    },
    created() {
      this.fetchCards();
    },
  };
  </script>
  
-->

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
    },
    methods: {
        changeCard(){
            this.$emit('filter')
        }
    }
}
</script>
<style lang="scss" scoped>
    
</style>