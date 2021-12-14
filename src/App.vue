// Html goes here..

<template>
  <div id="app">
    <pokemon-list allPokemon="Hello.."></pokemon-list>
  </div>
</template>


// JS goes here..

<script>
import PokemonList from './components/PokemonList.vue';

export default {
  name: 'App',
  data(){
    return{
        allPokemon: [],
    }
  },
  components: {
    "pokemon-list": PokemonList,
  }
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



