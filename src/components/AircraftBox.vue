<template>
   
    
    <div v-for="aircraft of aircrafts" :key="aircraft.id" >

     
       <SingleAircraft :aircraft=aircraft />

    </div>

</template>
<script>
import SingleAircraft from './SingleAircraft.vue'

export default {
    name: 'AircraftBox',
    props:{
        aircrafts: Array
    },
    components:{
        SingleAircraft
    }
    
}
</script>
<style scoped>

</style>
