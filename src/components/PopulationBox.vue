<template>
  <div class="populationbox">
     <div v-for="population in population" :key="population.id" >
             <PopulaTion :population="population"/>
     </div>
     <TopCities :cities="topCities" />
  </div>
  </template>
  <script>
   import PopulaTion from "./Population.vue"
   export default{
  name: 'PopulationBox',
  components: {
    PopulaTion
  },
  props: {
  population: Array
  }
  }
  </script>
  <style>
  .populationbox{
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 800px;
    
    background-repeat: no-repeat;
    background-size: cover;
  }
  </style>
  