<template>
  <div class="pokemon-list-item">
      <li>{{ pokemon.name }}</li>
  </div>
</template>



<script>
export default {
    name: "PokemonListItem",
    props: ["pokemon"],

}
</script>



<style>

</style>

