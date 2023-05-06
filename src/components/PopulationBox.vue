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
  background-image: url("https://ourworldindata.org/uploads/2019/10/Screen-Shot-2019-10-31-at-12.02.19-768x527.png");
  background-repeat: no-repeat;
  background-size: cover;
}
</style>

