<template>
  <div 
    :class="aircraft.id % 2 === 0 ? 'soft-green' : 'light-pink'" 
    class="aircraft-box"
  >
    <img :src="imageSrc" alt="Aircraft Image" class="aircraft-image" />
    <div class="aircraft-content">
      <h2>{{ aircraft.model }}</h2>
      <h4>Type: {{ aircraft.type }}</h4>
      <h4>Capacity: {{ aircraft.capacity }}</h4>
      <h4>Range Km: {{ aircraft.range_km }}</h4>
      <h4>Engine type: {{ aircraft.engine_type }}</h4>
      <h4>Manufacturer: {{ aircraft.manufacturer }}</h4>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleAircraft",
  props: {
    aircraft: Object,
  },
  computed: {
    imageSrc() {
      // Dynamically construct the image path based on the aircraft ID
      return require(`@/assets/imgs/img0${this.aircraft.id.toString().padStart(1)}.jpeg`);
    },
  },
};
</script>

<style scoped>
.aircraft-box {
  display: grid;
  grid-template-columns: 1fr 1fr; /* Image takes 150px, content takes the rest */
  align-items: center; /* Vertically align items */
  gap: 1em; /* Space between grid items */
  transition: transform 0.3s ease, box-shadow 0.3s ease; /* Smooth hover effect */
  color: #2c3e50;
  padding: 1em;
  text-align: left;
  width: 90%;
  height: 85%;
  margin: 10px auto;
  border: 1px solid #bfbfbf;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.aircraft-box:hover {
  transform: scale(1.05); /* Slightly increase size */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2); /* Deeper shadow on hover */
}

.aircraft-image {
  width: 100%; /* Adjust width to fit the grid column */
  height: 80%;
  border-radius: 5px; /* Optional rounded corners */
  object-fit: cover; /* Ensure the image looks good */
}

.aircraft-content h4 {
  margin: 2px;
}

.aircraft-content {
  display: grid;
  gap: 0px; /* Add spacing between text elements */
}

.soft-green {
  background-color: #d4edda; /* Soft green for a fresh look */
}

.light-pink {
  background-color: #ffe6e6; /* Light pink for a soft, warm tone */
}
</style>
