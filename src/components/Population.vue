<template>
<div class="popu">
    <ul><h1 style="color:white">{{population.city}}</h1></ul>
    <ul><h4>Rank : {{population.Rank}}</h4></ul>
    <ul><h4>Country : {{population.Country}}</h4></ul>
    <ul><h4>Population : {{population.Population}}</h4></ul>
    <ul><h4>Growth Rate :  {{population.Growth_Rate}}</h4></ul>
    </div>
</template>
<script>
export default{
    name: 'PopulaTion',
    props:{
        population: Array
    }
}
</script>
<style>
h4{
    margin: 2px;
}
.popu{
    background-color: #01040a;
    color:rgb(60, 86, 135);
    padding: 1em;
    border:3px solid rgb(100, 146, 211);
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    width:100%;
    height:250px;
}
.popu:hover {
 border: 5px solid #fefefc;
 color: #d9d0a1;
 box-shadow: 8px 8px #d9d0a1;
}
</style>