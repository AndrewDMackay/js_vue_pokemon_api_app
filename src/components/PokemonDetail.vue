<template>
  <div id="pokemon-detail">
      <h2>{{ pokemon.name }}</h2>
      <img :src="pokemon.sprites.front_shiny" />
  </div>
</template>



<script>
export default {
    name: "PokemonDetail",
    props: [ 'pokemon' ],
};
</script>



<style>

</style>