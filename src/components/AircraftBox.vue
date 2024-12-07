<template>
    <div class="aircraft-grid">
      <div v-for="aircraft of aircrafts" :key="aircraft.id" 
           :class="aircraft.id % 2 === 0 ? 'right-column' : 'left-column'">
        <SingleAircraft :aircraft="aircraft" />
      </div>
    </div>
  </template>
  
  <script>
  import SingleAircraft from "./SingleAircraft.vue";
  
  export default {
    name: "AircraftBox",
    props: {
      aircrafts: Array,
    },
    components: {
      SingleAircraft,
    },
  };
  </script>
  
  <style scoped>
  .aircraft-grid {
    display: grid;
    grid-template-columns: 1fr 1fr; /* Two columns: left and right */
    gap: 0.2vw; /* Space between grid items */
    width: 100vw; /* Adjust to fit viewport */
    margin: 0 ; /* Center horizontally */
  }
  
  /* Odd IDs: display in left column */
  .left-column {
    grid-column: 1; /* Place in the first column */
  }
  
  /* Even IDs: display in right column */
  .right-column {
    grid-column: 2; /* Place in the second column */
  }
  
 
  .aircraft-grid > div {
    margin-bottom: 2vh;
  }
  </style>
  