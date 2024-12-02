<template>
  <MyHeader aircraftName="Aircraft Model & Manufacturer Overview" manufacturerName="Aircraft Details" yourName="Author - Meghana Basavaraju" />
  <AircraftBox :aircrafts=aircrafts ></AircraftBox>
</template>

<script>

import MyHeader from './components/MyHeader.vue';
import AircraftBox from './components/AircraftBox.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    AircraftBox
  },
  data(){
    return {
      aircrafts: []
    }
  },

  methods:{
    //promoises
    async fetchaircrafts(){
      const res = await fetch('https://csci6655portfolioproject.netlify.app/api');
      const data = await res.json()
      console.log(data)
      return data
    }
  },
  async created(){
      this.aircrafts = await this.fetchaircrafts();
  }
}

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
