<template>
    <div>
        <h1> {{aircraftName}} </h1>
        <h2> {{manufacturerName}} </h2>
        <h4> {{yourName}} </h4>
    </div>
    </template>
    
    <script>
    
    export default{ // Exporting Default Object
        name: 'MyHeader',
        props:{ 
    
            aircraftName:String,
            manufacturerName:String,
            yourName: String
        }
    }
    
    </script>
    
    <style scoped>
    
    div{
        text-align: center;
    }
    
    </style>