<template>
  <div :class="aircraft.id % 2 === 0 ? 'soft-green' : 'light-pink'">
    <h2>{{ aircraft.model }}</h2>
    <h4>{{ aircraft.type }}</h4>
    <h4>{{ aircraft.capacity }}</h4>
    <h4>{{ aircraft.range_km }}</h4>
    <h4>{{ aircraft.engine_type }}</h4>
    <h4>{{ aircraft.manufacturer }}</h4>
  </div>
</template>

<script>
export default {
  name: "SingleAircraft",
  props: {
    aircraft: Array,
  },
};
</script>

<style scoped>
.soft-green {
  background-color: #d4edda; /* Soft green for a fresh look */
}

.light-pink {
  background-color: #ffe6e6; /* Light pink for a soft, warm tone */
}

h4 {
  margin: 2px;
}

div {
  color: #2c3e50; /* Darker text color for better contrast */
  padding: 1em;
  text-align: center;
  width: 80%;
  margin: 10px auto; /* Adds vertical spacing between blocks */
  border: 1px solid #bfbfbf; /* Subtle border for definition */
  border-radius: 8px; /* Rounded corners for a soft look */
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1); /* Slightly deeper shadow for better definition */
}
</style>
