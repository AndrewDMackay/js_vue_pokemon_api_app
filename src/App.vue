// Html goes here..

<template>
  <div id="app">
    <pokemon-detail :pokemon="selectedPokemon"></pokemon-detail>
    <pokemon-list :allPokemon="allPokemon"></pokemon-list>
  </div>
</template>


// JS goes here..

<script>
import PokemonDetail from './components/PokemonDetail.vue';
import PokemonList from './components/PokemonList.vue';
import { eventBus } from './main';

export default {
  name: 'App',
  data(){
    return{
        allPokemon: [],
        selectedPokemon: null,
    };
  },

  components: {
    "pokemon-detail": PokemonDetail,
    "pokemon-list": PokemonList,
  },

  methods: {
    fetchSinglePokemon: function(url){
      return fetch(this.selectedPokemon.url)
      .then(res => res.json())
      .then(data => this.selectedPokemon = data)
    }
  },

  mounted(){
    fetch('https://pokeapi.co/api/v2/pokemon?limit=151%27')
    .then(res => res.json())
    .then(data => (this.allPokemon = data.results));

    eventBus.$on('pokemon-selected', (pokemon) => {
      this.fetchSinglePokemon(pokemon.url);
    })
  },
};

</script>


// Styling goes here..

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>



