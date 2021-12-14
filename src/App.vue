<template>
  <div id="app">
    <ul>
      <li v-for="( item, index ) in items" :key="index">{{ item.name }}</li>
    </ul>
  </div>
</template>



<script>

export default {
  name: 'App',
  data(){
    return {
      items: [ 
        {name: "Milk", isPurchased: false},
        {name: "Cheese", isPurchased: true},
        {name: "Beans", isPurchased: false},
      ],
    };
  },
};

</script>



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
