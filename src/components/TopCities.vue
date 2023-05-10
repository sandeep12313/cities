<template>
  <div class="container">
    <HeaderTop TitleName="TOP POPULATED CITIES IN THE WORLD"  />
    <div class="About">
      <a href="about.html"><button>About Me</button></a>
      <button @click="showTopCities = true">Top Populated Cities in the World</button>
    </div>
    <PopulationBox :population="population"  />
    <TopCities v-if="showTopCities" :cities="topCities" @city-clicked="handleCityClicked" />
  </div>
</template>

<script>
import HeaderTop from './components/Header.vue'
import PopulationBox from './components/PopulationBox.vue'
import TopCities from './components/TopCities.vue'

export default {
  name: 'App',
  components: {
    HeaderTop,
    PopulationBox,
    TopCities
  },
  data() {
    return {
      population: [],
      topCities: [],
      showTopCities: false
    }
  },
  methods: {
    async fetchPopulation() {
      const res = await fetch('https://cities-idt9.onrender.com/api')
      const data = await res.json()
      return data.population
    },
    async fetchTopCities() {
      const res = await fetch('https://cities-idt9.onrender.com/api?topCities=true')
      const data = await res.json()
      return data.topCities
    },
    handleCityClicked(city) {
      console.log(city)
    }
  },
  watch: {
    showTopCities: async function(newValue) {
      if (newValue) {
        const data = await this.fetchTopCities();
        this.topCities = data;
      }
    }
  },
  created() {
    this.fetchPopulation().then(data => {
      this.population = data;
    })
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0px;
}

body {
  font-family: 'Montserrat', sans-serif;
}

.container {
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 40px;
  border-radius: 5px;
  width: 100%;
  background-color: rgb(11, 11, 11);
}

div {
  margin-bottom: 0.5em;
  padding: 10px;
}

.About {
  width: 100%;
}

a {
  text-decoration: none;
  color: rgb(2, 7, 16);
}

button {
  font-size: 30px;
  font-family: 'Times New Roman', Times, serif;
  background-color: rgb(193, 218, 224);
  width: 100%;
  border: 3px solid rgb
}


</style>